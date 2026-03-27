---
title: "Kintone REST API"
description: 'Documents for REST APIs for App, record, file and Space management.'
weight: 300
product: "kintone"
layout: overview
hasToc: false
aliases:
  - "/en/id/67355f93492464d0baf4a148/"
---

### Apps {#apps}

| Category | API | Method | URL |
| :-- | :-- | :-- | :-- |
| **Apps** | Get App | GET | [/k/v1/app.json](/docs/kintone/rest-api/apps/get-app/) |
|  | Get Apps | GET  | [/k/v1/apps.json](/docs/kintone/rest-api/apps/get-apps/) |
|  | Add Preview App | POST  | [/k/v1/preview/app.json](/docs/kintone/rest-api/apps/add-app/) |
| **Deploy** | Deploy App Settings | POST  | [/k/v1/preview/app/deploy.json](/docs/kintone/rest-api/apps/settings/deploy-app-settings/) |
|  | Get App Deploy Status | GET  | [/k/v1/preview/app/deploy.json](/docs/kintone/rest-api/apps/settings/get-app-deploy-status/) |
| **Form Fields** | Get Form Fields | GET  | [/k/v1/app/form/fields.json<br />/k/v1/preview/app/form/fields.json](/docs/kintone/rest-api/apps/form/get-form-fields/) |
|  | Add Form Fields | POST  | [/k/v1/preview/app/form/fields.json](/docs/kintone/rest-api/apps/form/add-form-fields/) |
|  | Update Form Fields | PUT  | [/k/v1/preview/app/form/fields.json](/docs/kintone/rest-api/apps/form/update-form-fields/) |
|  | Delete Form Fields | DELETE  | [/k/v1/preview/app/form/fields.json](/docs/kintone/rest-api/apps/form/delete-form-fields/) |
| **Form Layout** | Get Form Layout | GET  | [/k/v1/app/form/layout.json<br />/k/v1/preview/app/form/layout.json](/docs/kintone/rest-api/apps/form/get-form-layout/) |
|  | Update Form Layout | PUT  | [/k/v1/preview/app/form/layout.json](/docs/kintone/rest-api/apps/form/update-form-layout/) |
| **Views** | Get Views | GET  | [/k/v1/app/views.json<br />/k/v1/preview/app/views.json](/docs/kintone/rest-api/apps/view/get-views/) |
|  | Update Views | PUT  | [/k/v1/preview/app/views.json](/docs/kintone/rest-api/apps/view/update-views/) |
| **General Settings** | Get General Settings | GET  | [/k/v1/app/settings.json<br />/k/v1/preview/app/settings.json](/docs/kintone/rest-api/apps/settings/get-general-settings/) |
|  | Update General Settings | PUT  | [/k/v1/preview/app/settings.json](/docs/kintone/rest-api/apps/settings/update-general-settings/) |
| **Process Management** | Get Process Management Settings | GET  | [/k/v1/app/status.json<br />/k/v1/preview/app/status.json](/docs/kintone/rest-api/apps/settings/get-process-management-settings/) |
|  | Update Process Management Settings | PUT  | [/k/v1/preview/app/status.json](/docs/kintone/rest-api/apps/settings/update-process-management-settings/) |
| **Customization** | Get Customization | GET  | [/k/v1/app/customize.json<br />/k/v1/preview/app/customize.json](/docs/kintone/rest-api/apps/settings/get-customization/) |
|  | Update Customization | PUT  | [/k/v1/preview/app/customize.json](/docs/kintone/rest-api/apps/settings/update-customization/) |
| **App Permissions** | Get App Permissions | GET  | [/k/v1/app/acl.json<br />/k/v1/preview/app/acl.json](/docs/kintone/rest-api/apps/settings/get-app-permissions/) |
|  | Update App Permissions | PUT  | [/k/v1/app/acl.json<br />/k/v1/preview/app/acl.json](/docs/kintone/rest-api/apps/settings/update-app-permissions/) |
| **Record Permissions** | Get Record Permissions | GET  | [/k/v1/record/acl.json<br />/k/v1/preview/record/acl.json](/docs/kintone/rest-api/apps/settings/get-record-permissions/) |
|  | Update Record Permissions | PUT  | [/k/v1/record/acl.json<br />/k/v1/preview/record/acl.json](/docs/kintone/rest-api/apps/settings/update-record-permissions/) |
| **Field Permissions** | Get Field Permissions | GET  | [/k/v1/field/acl.json<br />/k/v1/preview/field/acl.json](/docs/kintone/rest-api/apps/settings/get-field-permissions/) |
|  | Update Field Permissions | PUT  | [/k/v1/field/acl.json<br />/k/v1/preview/field/acl.json](/docs/kintone/rest-api/apps/settings/update-field-permissions/) |
| **General Notifications** | Get General Notification Settings | GET  | [/k/v1/app/notifications/general.json<br />/k/v1/preview/app/notifications/general.json](/docs/kintone/rest-api/apps/settings/get-general-notification-settings/) |
| | Update General Notification Settings | PUT  | [/k/v1/preview/app/notifications/general.json](/docs/kintone/rest-api/apps/settings/update-general-notification-settings/) |
| **Per Record Notifications** | Get Per Record Notification Settings | GET  | [/k/v1/app/notifications/perRecord.json<br />k/v1/preview/app/notifications/perRecord.json](/docs/kintone/rest-api/apps/settings/get-per-record-notification-settings/) |
| | Update Per Record Notification Settings | PUT | [k/v1/preview/app/notifications/perRecord.json](/docs/kintone/rest-api/apps/settings/update-per-record-notification-settings/) |
| **Reminder Notifications** | Get Reminder Notification Settings | GET  | [/k/v1/app/notifications/reminder.json<br />/k/v1/preview/app/notifications/reminder.json](/docs/kintone/rest-api/apps/settings/get-reminder-notification-settings/) |
| | Update Reminder Notification Settings | PUT  | [/k/v1/preview/app/notifications/reminder.json](/docs/kintone/rest-api/apps/settings/update-reminder-notification-settings/) |
| **Graph Settings** | Get Graph Settings | GET  | [/k/v1/app/reports.json<br />/k/v1/preview/app/reports.json](/docs/kintone/rest-api/apps/report/get-graph-settings/) |
| | Update Graph Settings | PUT  | [/k/v1/preview/app/reports.json](/docs/kintone/rest-api/apps/report/update-graph-settings/) |
| **Action Settings** | Get Action Settings | GET  | [/k/v1/app/actions.json<br />/k/v1/preview/app/actions.json](/docs/kintone/rest-api/apps/settings/get-action-settings/) |
| | Update Action Settings | PUT  | [/k/v1/preview/app/actions.json](/docs/kintone/rest-api/apps/settings/update-action-settings/) |
| **Get Form** | Get Form | GET  | [/k/v1/form.json<br />/k/v1/preview/form.json](/docs/kintone/rest-api/apps/form/get-form/) |
| **Move App** | Move App to Space | POST  | [/k/v1/app/move.json](/docs/kintone/rest-api/apps/settings/move-app/) |
| **Plug-ins** | Get App Plug-ins | GET  | [/k/v1/app/plugins.json](/docs/kintone/rest-api/apps/settings/get-app-plugins/) |
| | Add Plug-ins | POST  | [/k/v1/app/plugins.json](/docs/kintone/rest-api/apps/settings/add-app-plugins/) |
| **Admin Notes** | Get App Admin Notes | GET  | [/k/v1/app/adminNotes.json](/docs/kintone/rest-api/apps/get-app-admin-notes/) |
| | Update App Admin Notes | PUT  | [/k/v1/app/adminNotes.json](/docs/kintone/rest-api/apps/update-app-admin-notes/) |

\* Certain APIs concerning Apps can be executed only on form settings that have not been applied to the live App (ie. changes were made to the form settings but the App has not been updated), only on the live App, or either.

\* The URL path in the case of settings that have not yet been updated to the live App is '_/k/v1/**preview**/xxxx.json'._ Refer to each individual document for details.

### Records {#records}

| Category | API | Method | URL |
| :-- | :-- | :-- | :-- |
| **Record** | Get Record | GET  | [/k/v1/record.json](/docs/kintone/rest-api/records/get-record/) |
| | Get Records | GET  | [/k/v1/records.json](/docs/kintone/rest-api/records/get-records/) |
| | Add Record | POST  | [/k/v1/record.json](/docs/kintone/rest-api/records/add-record/) |
| | Add Records | POST  | [/k/v1/records.json](/docs/kintone/rest-api/records/add-records/) |
| | Update Record | PUT  | [/k/v1/record.json](/docs/kintone/rest-api/records/update-record/) |
| | Update Records | PUT  | [/k/v1/records.json](/docs/kintone/rest-api/records/update-records/) |
| | Delete Records | DELETE  | [/k/v1/records.json](/docs/kintone/rest-api/records/delete-records/) |
| **Cursor** | Get Cursor | GET  | [/k/v1/records/cursor.json](/docs/kintone/rest-api/records/get-cursor/) |
| | Add Cursor | POST  | [/k/v1/records/cursor.json](/docs/kintone/rest-api/records/create-cursor/) |
| | Delete Cursor | DELETE  | [/k/v1/records/cursor.json](/docs/kintone/rest-api/records/delete-cursor/) |
| **Comments** | Get Comments | GET  | [/k/v1/record/comments.json](/docs/kintone/rest-api/records/get-comments/) |
| | Add Comment | POST  | [/k/v1/record/comment.json](/docs/kintone/rest-api/records/add-comment/) |
| | Delete Comment | DELETE  | [/k/v1/record/comment.json](/docs/kintone/rest-api/records/delete-comment/) |
| **Bulk Request** | Bulk Request | POST  | [/k/v1/bulkRequest.json](/docs/kintone/rest-api/records/bulk-request/) |
| **Process Management** | Update Status | PUT  | [/k/v1/record/status.json](/docs/kintone/rest-api/records/update-status/) |
| | Update Multiple Statuses | PUT  | [/k/v1/records/status.json](/docs/kintone/rest-api/records/update-statuses/) |
| | Update Assignees | PUT  | [/k/v1/record/assignees.json](/docs/kintone/rest-api/records/update-assignees/) |
| **Record Permissions** | Evaluate Record Permissions | GET  | [/k/v1/records/acl/evaluate.json](/docs/kintone/rest-api/records/evaluate-record-permissions/) |

### Files {#files}

| Category | API | Method | URL |
| :-- | :-- | :-- | :-- |
| **File** | Download File | GET  | [/k/v1/file.json](/docs/kintone/rest-api/files/download-file/) |
| | Upload File | POST  | [/k/v1/file.json](/docs/kintone/rest-api/files/upload-file/) |

### Spaces {#spaces}

| Category | API | Method | URL |
| :-- | :-- | :-- | :-- |
| **Space** | Get Space | GET  | [/k/v1/space.json](/docs/kintone/rest-api/spaces/get-space/) |
| | Add Space From Template | POST  | [/k/v1/template/space.json](/docs/kintone/rest-api/spaces/add-space-from-template/) |
| | Update Space Body | PUT  | [/k/v1/space/body.json](/docs/kintone/rest-api/spaces/update-space-body/) |
| | Delete Space | DELETE  | [/k/v1/space.json](/docs/kintone/rest-api/spaces/delete-space/) |
| **Space Members** | Get Space Members | GET  | [/k/v1/space/members.json](/docs/kintone/rest-api/spaces/get-space-members/) |
| | Update Space Members | PUT  | [/k/v1/space/members.json](/docs/kintone/rest-api/spaces/update-space-members/) |
| **Thread** | Add Thread Comment | POST  | [/k/v1/space/thread/comment.json](/docs/kintone/rest-api/spaces/add-thread-comment/) |
| | Add Thread | POST  | [/k/v1/space/thread.json](/docs/kintone/rest-api/spaces/add-thread/) |
| | Update Thread | PUT  | [/k/v1/space/thread.json](/docs/kintone/rest-api/spaces/update-thread/) |
| **Guests** | Add Guests | POST  | [/k/v1/guests.json](/docs/kintone/rest-api/spaces/add-guests/) |
| | Update Guest Members | PUT  | [/k/guest/\&lt;SpaceID\&gt;/v1/space/guests.json](/docs/kintone/rest-api/spaces/update-guest-members/) |
| | Delete Guests | DELETE  | [/k/v1/guests.json](/docs/kintone/rest-api/spaces/delete-guests/) |

### Plug-ins {#plugins}

| Category | API | Method | URL |
| :-- | :-- | :-- | :-- |
| **Plug-ins** | Get Installed Plug-ins | GET | [/k/v1/plugins.json](/docs/kintone/rest-api/plugins/get-plugins/) |
| | Install Plug-in | POST | [/k/v1/plugin.json](/docs/kintone/rest-api/plugins/add-plugin/) |
| | Update Plug-in | PUT | [/k/v1/plugin.json](/docs/kintone/rest-api/plugins/update-plugin/) |
| | Uninstall Plug-in | DELETE | [/k/v1/plugin.json](/docs/kintone/rest-api/plugins/delete-plugin/) |
| | Get Plug-in Apps | GET | [/k/v1/plugin/apps.json](/docs/kintone/rest-api/plugins/get-plugin-apps/) |
| | Get Required Plug-ins | GET |  [/k/v1/plugins/required.json](/docs/kintone/rest-api/plugins/get-required-plugins/) |

### API Info {#api-info}

| Category | API | Method | URL |
| :-- | :-- | :-- | :-- |
| **Kintone REST API** | Get API List | GET  | [/k/v1/apis.json](/docs/kintone/rest-api/apis/get-apis/) |
| | Get API Schema | GET  | [/k/v1/apis/\*.json](/docs/kintone/rest-api/apis/get-api-schema/) |
