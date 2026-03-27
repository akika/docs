---
title: Field Change Event
description: 'Events triggered when a specified field value change during an inline editing of a record '
tags: []
product: kintone
weight: 500
hastoc: False
aliases:
  - "/en/id/53b0addcb22e876a199ba578/"
---

### Field Change Event - `app.record.index.edit.change.(fieldcode)` {#field-change-event}

An event triggered when a specified field value changes during an inline editing of a record on the record list.

{{< image alt="Field Change Event" src="field-change-event.png" width="600" height="263" >}}

#### Function {#function}

`app.record.index.edit.change.(fieldcode)`

#### Fields That Can Be Specified {#fields-that-can-be-specified}

- *Single-line text
- *Number
- Radio button
- Check box
- Multi-choice
- Drop-down
- Date
- Time
- Date and time
- User selection
- Department selection
- Group selection

*An event is triggered when the field loses focus or when a value is set via a lookup field.

#### Properties of the Event Object {#properties-of-the-event-object}

| PROPERTY | TYPE | DESCRIPTION |
| :-- | :-- | :-- |
| type | String | The event type.<br>Returns `app.record.index.edit.change.(fieldcode)`. |
| appId | Number | The App ID. |
| record | Object | A record object including data inputted by the user at the time of the event.<br>For more information, refer to the following article:<br>[Field Types](/docs/kintone/overview/field-types/) |
| recordId | Number | The Record ID. |
| changes | Object | An object including data of changed fields and rows. |
| changes.field | Object | An object of the changed field.<br>For more information, refer to the following article:<br>[Field Types](/docs/kintone/overview/field-types/) |
| changes.row | null | Table row data.<br>Always returns `null` as table fields cannot be modified on the record list. |

#### Available Event Object Actions {#available-event-object-actions}

- [Overwrite field values](/docs/kintone/js-api/events/event-object-actions/#record-list-overwrite-field-values)
- [Enable/Disable field edits](/docs/kintone/js-api/events/event-object-actions/#record-list-enable-disable-field-edits)
- [Show field errors](/docs/kintone/js-api/events/event-object-actions/#record-list-show-field-errors)
- [Show record errors](/docs/kintone/js-api/events/event-object-actions/#record-list-show-record-errors)
- [Get the object of the edited field](/docs/kintone/js-api/events/event-object-actions/#record-list-get-the-object-of-the-edited-field)

#### Running Actions after Waiting for Asynchronous Operations to Finish {#running-actions-after-waiting-for-asynchronous-operations-to-finish}

By returning a `Promise` object, you can run actions after waiting for asynchronous operations to finish. Refer to the sample code on the following article:  
[Save Event](/docs/kintone/js-api/events/record-create-events/save-event/)

#### Limitations {#limitations}

- This event is only available on the Desktop, and not on the mobile.
- Events are not triggered for fields are not listed in the following section:  
  [Fields that can be specified](#fields-that-can-be-specified)
- The value of a calculated field retrieved via the event object depends on whether the field is displayed in the record list:  
  - If displayed in the list: Returns an empty string
  - If not displayed in the list: Returns the value before recalculation
- Refer to the Limitations section of the following article:  
  [Event Handling](/docs/kintone/js-api/events/event-handling/#limitations)
