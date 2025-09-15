---
title: Post-processing event handler
description: Learn about Post-processing event handler
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
---
# Post-processing event handler {#id175UB30E05Z}

## UUID and Cloud Service

Adobe Experience Manager Guides exposes `com/adobe/guides/postprocess/complete` event that is used to perform any post-processing operations. This event is triggered whenever an operation is performed on a DITA file. The following operations on a DITA file trigger this event:

- Upload
- Create
- Modify

>[!NOTE]
>
> The post processing event is triggered by enabling the `fire.processing.events` flag.

You need to create an Adobe Experience Manager event handler to read the properties available in this event and do further processing.

Event details are explained below:

**Event name**:

```
com/adobe/guides/postprocess/complete 
```

**Parameters**:

|Name|Type|Description|
|----|----|-----------|
|`path`|String|The path of the file that triggered this event. Typically, this is the file on which an operation has been performed.|
|`eventType`|String|The type of event i.e. CREATE or MODIFY.|
|`status`|String|The return status for the operation performed. The possible options are: - <br>- SUCCESS: The post-processing operation completed successfully. <br>- FAILED: The post-processing operation failed due to some error.|
|`errorMsg`|String|The error message in case of post-processing operation failure.|
|`uuid`|String|The UUID of the file that triggered this event. Typically, this is the file on which an operation has been performed.|

**Sample Event Listerner**


```
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/guides/postprocess/complete",
        })
public class PostProcessCompleteEventHandler implements EventHandler {

    protected final Logger log = LoggerFactory.getLogger(this.getClass());

    @Override
    public void handleEvent(final Event event) {
        Set<String> propertyNames = new HashSet<>(Arrays.asList(event.getPropertyNames()));
        Map<String, String> properties = new HashMap<>();
        properties.put("path", (String) event.getProperty("path"));
        properties.put("eventType", (String) event.getProperty("eventType"));
        properties.put("status", (String) event.getProperty("status"));
        if(propertyNames.contains("errorMsg")) {
            properties.put("errorMsg", (String) event.getProperty("errorMsg"));
        }
        if (propertyNames.contains("uuid")) {
            properties.put("uuid", (String) event.getProperty("uuid"));
        }
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
    }
}
```

## Non UUID 


Adobe Experience Manager Guides exposes com/adobe/fmdita/postprocess/complete event that is used to perform any post-processing operations. This event is triggered whenever an operation is performed on a DITA file. The following operations on a DITA file trigger this event:

>[!NOTE]
>
> This event is not triggered for the Deletion operation in AEM 6.1.

- Upload
- Creation
- Modification
- Deletion

You need to create an Adobe Experience Manager event handler to read the properties available in this event and do further processing.

Event details are explained below:

**Event name**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parameters**:

|Name|Type|Description|
|----|----|-----------|
|`path`|String|The path of the file that triggered this event. Typically, this is the file on which an operation has been performed.|
|`status`|String|The return status for the operation performed. The possible options are: - <br>- SUCCESS: The post-processing operation completed successfully. <br>- COMPLETED WITH ERRORS: The post-processing operation completed, but with some errors. <br>- FAILED: The post-processing operation failed due to some error.|
|`message`|String|In case the status is COMPLETED WITH ERRORS or FAILED, this parameter contains the details about the error or the reason of failure.|
|`operation`|String|The post-processing operation performed on the file. The possible options are:<br>- Addition <br>- Updation <br>- Deletion|
