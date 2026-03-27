---
title: Onload Event
description: 'Events triggered when the record list page is displayed.'
tags: []
product: kintone
weight: 100
tocEndLevel: 3
aliases:
  - "/en/id/0d01f23fe9c8bc7a11b14ef4/"
---

### Onload Event (desktop) - `app.record.index.show` {#onload-event-desktop}

An event triggered after the record list page is displayed on desktop.

{{< image alt="Record List Event(Desktop)" src="record-list-event-desktop.png" width="600" height="309" >}}

#### Function {#onload-desktop-function}

`app.record.index.show`

#### Sample {#onload-desktop-sample}

<!-- eslint-disable strict -->
```js
kintone.events.on('app.record.index.show', function(event) {
  console.log(event);
  // Displays contents of event object in console
  // Record data is contained in event.records
});
```

#### Triggered Timing {#onload-desktop-triggered-timing}

- General:  
  - After displaying the record list page
  - After displaying the record list page when clicking the **Next** or **Previous** arrow icons (the icons are displayed when all records cannot be fit into one page)
  - After applying filter records on the record list page
  - After changing the category on the record list page
- List view type:  
  - After sorting the record order when clicking the field titles on the record list page
- Calendar view type:  
  - After changing the year or month on the record list page

#### Properties of the Event Object {#onload-desktop-properties-of-the-event-object}

| PROPERTY | TYPE | DESCRIPTION |
| :-- | :-- | :-- |
| type | String | The event type.<br>Returns `app.record.index.show`. |
| appId | Number | The App ID. |
| viewId | Number | The View ID of the record list. |
| viewName | String | The View Name of the record list. |
| viewType | String | The type of the record list. Possible values are `list`, `calendar`, or `custom`. |
| records | Array or Object | Differs depending on the `viewType`:<ul><li>`list`: An array of record objects</li><li>`calendar`: An object including the date string as the key, and an array of record objects as the value<br>A `calendar` example:<pre>{<br>  "2015-04-01": [record1, record2],<br>  "2015-04-20": [record1]<br>}</pre></li><li>`custom` with pagination enabled: An array of record objects</li><li>`custom` with pagination disabled: An empty array</li></ul> |
| date | String | Differs depending on the `viewType`:<ul><li>`calendar`: The month shown in the `calendar` view. April 2015 will be `2015-04`</li><li>All others: `null`</li></ul> |
| offset | Number | Differs depending on the `viewType`:<ul><li>`list`: The offset of the list</li><li>`calendar`: `null`</li><li>`custom` with pagination enabled: The offset of the list</li><li>`custom` with pagination disabled: `0`</li></ul> |
| size | Number | Differs depending on the `viewType`:<ul><li>`list`: The number of records in the list</li><li>`calendar`: `null`</li><li>`custom` with pagination enabled: The number of records in the list</li><li>`custom` with pagination disabled: `0`</li></ul> |

#### Available Event Object Actions {#onload-desktop-available-event-object-actions}

By returning a `Promise` object in the event handler, the next operations can be processed after waiting for asynchronous processes in the event handler to finish.

### Onload Event (mobile) - `mobile.app.record.index.show` {#onload-event-mobile}

An event triggered after the record list page is displayed on mobile.

{{< image alt="Record List Event(Mobile)" src="record-list-event-mobile.png" width="189" height="300" >}}

#### Function {#onload-mobile-function}

`mobile.app.record.index.show`

#### Triggered Timing {#onload-mobile-triggered-timing}

- General:  
  - After displaying the record list page
  - After displaying the record list page when clicking the **Next** or **Previous** arrow icons (the icons are displayed when all records cannot be fit into one page)
  - After applying filter records on the record list page
  - After changing the category on the record list page
- List view type:  
  - After sorting the record order when clicking the field titles on the record list page
- Calendar view type:  
  - After changing the year or month on the record list page

#### Properties of the Event Object {#onload-mobile-properties-of-the-event-object}

| PROPERTY | TYPE | DESCRIPTION |
| :-- | :-- | :-- |
| type | String | The event type.<br>Returns `mobile.app.record.index.show`. |
| appId | Number | The App ID. |
| viewId | Number | The View ID of the record list. |
| viewName | String | The View Name of the record list. |
| viewType | String | The type of view of the record list. *Available only if the View Type is **List View** or **Custom View** |
| records | Array | An array of record objects. *Available only if the View Type is **List View** or **Custom View** |
| offset | Number | The offset of the list. *Available only if the View Type is **List View** or **Custom View** |
| size | Number | The number of records in the list. *Available only if the View Type is **List View** or **Custom View** |

#### Available Event Object Actions {#onload-mobile-available-event-object-actions}

By returning a `Promise` object in the event handler, the next operations can be processed after waiting for asynchronous processes in the event handler to finish.

### Limitations {#limitations}

- Refer to the Limitations section of the following article for more details:  
  [Event Handling](/docs/kintone/js-api/events/event-handling/#limitations)
