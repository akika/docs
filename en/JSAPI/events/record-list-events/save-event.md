---
title: Save Event
description: 'Events triggered when the save button is clicked.'
tags: []
product: kintone
weight: 300
hastoc: False
aliases:
  - "/en/id/35d7d2063e5176afd7af51a4/"
---

### Save Event - `app.record.index.edit.submit` {#save-event}

An event triggered when the save button of the inline editing is clicked on the record list.

{{< image alt="Save Event" src="save-submit-event.png" width="309" height="210" >}}

#### Function {#save-function}

`app.record.index.edit.submit`

#### Properties of the Event Object {#properties-of-the-event-object}

| PROPERTY | TYPE | DESCRIPTION |
| :-- | :-- | :-- |
| appId | Number | The App ID. |
| recordId | Number | The Record ID. |
| record | Object | A record object that holds data inputted by the user.<br>For more information, refer to the following article:<br>[Field Types](/docs/kintone/overview/field-types/) |
| type | String | The event type.<br>Returns `app.record.index.edit.submit`. |

#### Cancel Actions {#cancel-actions}

Actions can be cancelled by doing one of the following:

- [Show field errors](/docs/kintone/js-api/events/event-object-actions/#record-list-show-field-errors)
- [Show record errors](/docs/kintone/js-api/events/event-object-actions/#record-list-show-record-errors)
- return `false`

#### Available Event Object Actions {#available-event-object-actions}

- [Overwrite field values](/docs/kintone/js-api/events/event-object-actions/#record-list-overwrite-field-values)
- [Show field errors](/docs/kintone/js-api/events/event-object-actions/#record-list-show-field-errors)
- [Show record errors](/docs/kintone/js-api/events/event-object-actions/#record-list-show-record-errors)

#### Limitations {#limitations}

- This event is only available on the Desktop, and not on the mobile.
- The value of a calculated field retrieved via the event object depends on whether the field is displayed in the record list:  
  - If displayed in the list: Returns an empty string
  - If not displayed in the list: Returns the value before recalculation
- Refer to the Limitations section of the following article for more details:  
  [Event Handling](/docs/kintone/js-api/events/event-handling/#limitations)
