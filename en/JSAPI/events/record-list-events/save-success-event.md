---
title: Save Success Event
description: 'Events triggered after the record has been successfully saved.'
tags: []
product: kintone
weight: 400
hastoc: False
aliases:
  - "/en/id/cc052cea1326ef32e22bb794/"
---

### Save Success Event - `app.record.index.edit.submit.success` {#save-success-event}

An event triggered after the record has been successfully saved after clicking the save button on the record list page on the desktop.

#### Function {#function}

`app.record.index.edit.submit.success`

#### Properties of the Event Object {#properties-of-the-event-object}

| PROPERTY | TYPE | DESCRIPTION |
| :-- | :-- | :-- |
| appId | Number | The App ID. |
| recordId | Number | The Record ID. |
| record | Object | A record object that holds data of the saved record. |
| type | String | The event type. |

#### Available Event Object Actions {#available-event-object-actions}

None

#### Sample showing the datetime the record was updated {#sample-showing-the-datetime-when-the-record-was-updated}


```js
// Display the updated date time after saving.
kintone.events.on('app.record.index.edit.submit.success', function(event) {
  var record = event.record;
  alert('The updated date time is ' + record.Updated_datetime.value + '.');
});
```

#### Limitations {#limitations}

- This event is only available on the Desktop.
- This event cannot be used with an app embedded on a space.
- The event will not trigger if the record does not successfully save.
- Refer to the Limitations section of the following article for more details:  
  [Event Handling](/docs/kintone/js-api/events/event-handling/#limitations)
