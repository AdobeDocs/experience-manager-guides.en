---
title: Jui Framework
description: Understanding Jui Framework
role: User, Admin
exl-id: c193cf90-5916-4d8c-88f1-be5014beca1c
TQID: https://experienceleague.adobe.com/AQFEy2bHTDHXq6QH8KTBOEzUvtA3Hf2ojhxvD0dsI7o
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Jui Framework

Before going into how to write extensions we'll understand the arcitecture of the framework.
So that we may extend it effectively.

## Introduction

JUI is a MVC framework on top of React and Adobe React Spectrum components. JUI is JSON User Interface. It consists of multiple git repositories.

JUI-Core is the core library with all logic to convert JSON config to working react components and link it with a relevant controller class instance.
JUI-React-Spectrum  library has wrapper widgets of Adobe React Spectrum components

## JUI Core Design

### MVC UI Design

![JUI MVC flow](./imgs/jui-mvc-flow.png)

### Widget

- Has a unique ID.
- Has an individual JSON file for view.
- Can have an own or shared Controller.
- Can use parent model or new model.
- Can have UI elements(React Components)
- Can have other widgets
- App is a Widgets

![JUI Widget](./imgs/jui-widget.png)

### Element

- Is an HTML/React Component.
- Does not have any model, its uses parent widget model.

### Event Handler

- Next(eventOpts)
  - To trigger event with some opts
- Subscribe(callback)
  - Get notification that event is fired with configuration

### App/Global Model

- Next(new value)
  - To publish new value
- Subscribe(callback)
  - To get notification for value changed
  - First time get old value
- GetValue()
  - To get current value

### Controller

- It should be extended from Controller class
- APIs
- CreateModel
  - To create child widget separate model
- InitEventHandler
  - To create child widget separate event handler
- RegisterCommands
  - To Register local, parent or app events
- Next(eventName, eventHandler)
  - To trigger event of child widget event handler, parent widget event handler or app event handler
- Subscribe(callback, eventHandler)
- SubscribeAppModel(callback)

### Sample App design

![Sample App](./imgs/jui-sample-app.png)
