---
title: Customising the app
description: Customising the app
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
---
# Customising the app

## Exposed functionality under extension framework

We have exposed a set of functions and getters under a `proxy` which can be used to access data, config and trigger events. Below is a list and how to access them.

```typescript
interface EventData {
  key?: string,
  keys?: string[]
  view?: any,
  next?: any,
  error?: any,
  completed?: any,
  id?: any
}

* getValue(key)
* setValue(key, value)
* subject // getter
* subscribe(opts: EventData)
* subscribeAppEvent(opts: EventData)
* subscribeAppModel(key, next)
* subscribeParentEvent(opts: EventData)
* parentEventHandlerNext(eventName: string, opts: any)
* appModelNext(eventName:string, opts) 
* appEventHandlerNext(eventName:string, opts)
* next(eventName:string, opts, eventHandler?)
* viewConfig //getter
* args //getter
```

Our app follows a MVC (Model, View, Controller) structure

## Model

The model defines the various attributes and store their values. The values of the various attributes stored in the model can be accessed from the controller using the syntax

```typescript
this.getValue('attributeName')
```

For customisation in the app, all newly created attributes will be added under a map in the model.
To set a new attribute in the model we will use the following syntax in the controller:

```typescript
// If a key is not already in model then it will be added to extraProps
this.setValue('key', value)
```

To access an attribute added to the model we will use the following syntax:

```typescript
const value = this.getValue("key")
```

## View

The view defines the UI of the app. We use JSON files to define the view of our files. Here, we define the components, the css (as given in the extraclass of components) and render the values stored in the model.
In our app, each view is defined using a JSON. The JSONs are referenced using their unique IDs called a `id`.

## Controller

The controller is used to handle events and process the data. The controller is used to fetch and send data from the server, it is the interface between what is displayed on the UI and stored on the backend.

- To set values at initialisation, we use the `init` function.
- To add a method the the controller we use the following syntax:

```typescript
methodName: function(args){
    // functionality
}
```

The `methodName` here serves as the `key` to reference the method in the JSON (view) or in other functions

- To call a method in the controller we use the syntax

```typescript
this.next('methodName', args)
```

## Example

Let us now use a simple example to show how these 3 components interact with each other.
We will add a button which switches its label value on a click

### View Example

Below we define the JSON for a button that shows a dynamic text stored in the model under the variable name `buttonLabel`.
In this example, clicking the button changes its label.

```JSON
{
    "component": "button",
    "label": "@extraProps.buttonLabel",
    "variant": "cta",
    "on-click": "switchButtonLabel",
}
```

### Model Example

in this case, `extraProps.buttonLabel` holds the label of the button

### Controller Example

```typescript
  controller: {
    init: function () {
      this.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

Below GIF shows the above code in action
![basic_customisation](imgs/basic_customisation.gif "Basic customisation button")


### View config example

In this case we access search mode event using `viewConfig` and trigger an event to update it

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        console.log('Logging view config ', this.viewConfig)
        this.next(this.viewConfig.items[1].searchModeChangedEvent, { searchMode: true })
      }
    }
  }
```

### Subscribe example

In this case we add subscription on file rename to console log when file rename option is clicked

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribe({
          key: 'rename',
          next: () => { console.log('rename using extension') }
        })
      }
    }
  }
```

### Subscribe app event example

In this case we console log on active document changed (changing tabs in editor UI)

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppEvent({
          key: 'app.active_document_changed',
          next: () => { console.log('Extension: active document changed') }
        })
      }
    }
  }
```

### Subscribe app model events example

Example for subscribing app model events such as `app.mode`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppModel('app.mode',
          () => { console.log('app mode subs') }
        )
      }
    }
  }
```

### Parent controller events example

In this we add subscription on `tabChange` event which is an event of `left_panel_container` controller which acts 
as parent controller for `repository_panel`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeParentEvent({
          key: 'tabChange',
          next: () => { console.log('tab change subs') }
        })
        this.parentEventHandlerNext('tabChange', {
          data: 'map_panel'
        )
      }
    }
  }
```

### App model and app controller next

They can be directly triggered by knowing correct event to fire and its data

```typescript
  { 
    id: 'file_options', 
    controller: {
      init: function () {
        this.appModelNext('app.mode', 'author')
        this.appEventHandlerNext('app.active_document_changed', 'active doc changed')   
      }
    }
  } 
```
