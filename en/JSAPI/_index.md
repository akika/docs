---
title: "Kintone JavaScript API"
description: 'Documents for JavaScript APIs for Kintone UI/UX manipulation.'
weight: 300
product: "kintone"
layout: overview
hasToc: false
aliases:
  - "/en/id/2434bb47c9be5a49e7d6cd49/"
---

Refer to the following article on how to use Kintone's event handlers:  
[Event Handling](/docs/kintone/js-api/events/event-handling/)

### Events {#events}

#### Record List Events {#record-list-events}

| Triggered Timing | Desktop | Mobile |
| :-- | :-- | :-- |
| Onload Event | [app.record.index.show](/docs/kintone/js-api/events/record-list-events/onload-event/#onload-event-desktop) | [mobile.app.record.index.show](/docs/kintone/js-api/events/record-list-events/onload-event/#onload-event-mobile) |
| Inline Edit Event | [app.record.index.edit.show](/docs/kintone/js-api/events/record-list-events/inline-edit-event/) |   |
| Save Event | [app.record.index.edit.submit](/docs/kintone/js-api/events/record-list-events/save-event/) |   |
| Save Success Event | [app.record.index.edit.submit.success](/docs/kintone/js-api/events/record-list-events/save-success-event/) |   |
| Field Change Event | [app.record.index.edit.change.(fieldcode)](/docs/kintone/js-api/events/record-list-events/field-change-event/) |   |
| Delete Event | [app.record.index.delete.submit](/docs/kintone/js-api/events/record-list-events/delete-event/) |  |

#### Record Details Events {#record-details-events}

| Triggered Timing | Desktop | Mobile |
| :-- | :-- | :-- |
| Onload Event | [app.record.detail.show](/docs/kintone/js-api/events/record-details-events/onload-event/#onload-event-desktop) | [mobile.app.record.detail.show](/docs/kintone/js-api/events/record-details-events/onload-event/#onload-event-mobile) |
| Delete Event | [app.record.detail.delete.submit](/docs/kintone/js-api/events/record-details-events/delete-event/) | [mobile.app.record.detail.delete.submit](/docs/kintone/js-api/events/record-details-events/delete-event/) |
| Update Status Event | [app.record.detail.process.proceed](/docs/kintone/js-api/events/record-details-events/update-status-event/) | [mobile.record.detail.process.proceed](/docs/kintone/js-api/events/record-details-events/update-status-event/) |

#### Record Create Events {#record-create-events}

| Triggered Timing | Desktop | Mobile |
| :-- | :-- | :-- |
| Onload Event | [app.record.create.show](/docs/kintone/js-api/events/record-create-events/onload-event/#onload-event-desktop) | [mobile.app.record.create.show](/docs/kintone/js-api/events/record-create-events/onload-event/#onload-event-mobile) |
| Save Event | [app.record.create.submit](/docs/kintone/js-api/events/record-create-events/save-event/) | [mobile.app.record.create.submit](/docs/kintone/js-api/events/record-create-events/save-event/) |
| Save Success Event | [app.record.create.submit.success](/docs/kintone/js-api/events/record-create-events/save-success-event/) | [mobile.app.record.create.submit.success](/docs/kintone/js-api/events/record-create-events/save-success-event/) |
| Field Change Event | [app.record.create.change.(fieldcode)](/docs/kintone/js-api/events/record-create-events/field-change-event/) | [mobile.app.record.create.change.(fieldcode)](/docs/kintone/js-api/events/record-create-events/field-change-event/) |

#### Record Edit Events {#record-edit-events}

| Triggered Timing | Desktop | Mobile |
| :-- | :-- | :-- |
| Onload Event | [app.record.edit.show](/docs/kintone/js-api/events/record-edit-events/onload-event/#onload-event-desktop) | [mobile.app.record.edit.show](/docs/kintone/js-api/events/record-edit-events/onload-event/#onload-event-mobile) |
| Save Event | [app.record.edit.submit](/docs/kintone/js-api/events/record-edit-events/save-event/) | [mobile.app.record.edit.submit](/docs/kintone/js-api/events/record-edit-events/save-event/)  |
| Save Success Event | [app.record.edit.submit.success](/docs/kintone/js-api/events/record-edit-events/save-success-event/) | [mobile.app.record.edit.submit.success](/docs/kintone/js-api/events/record-edit-events/save-success-event/) |
| Field Change Event | [app.record.edit.change.(fieldcode)](/docs/kintone/js-api/events/record-edit-events/field-change-event/) | [mobile.app.record.edit.change.(fieldcode)](/docs/kintone/js-api/events/record-edit-events/field-change-event/) |

#### Record Print Events {#record-print-events}

| Triggered Timing | Desktop | Mobile |
| :-- | :-- | :-- |
| Onload Event | [app.record.print.show](/docs/kintone/js-api/events/record-print-events/onload-event/) |   |

#### Graph Display Events {#graph-display-events}

| Triggered Timing | Desktop | Mobile |
| :-- | :-- | :-- |
| Onload Event | [app.report.show](/docs/kintone/js-api/events/graph-display-events/onload-event/) | [mobile.app.report.show](/docs/kintone/js-api/events/graph-display-events/onload-event/) |

#### Portal Display Events {#portal-display-events}

| Triggered Timing | Desktop | Mobile |
| :-- | :-- | :-- |
| Onload Event | [portal.show](/docs/kintone/js-api/events/portal-display-events/onload-event/#onload-event-desktop) | [mobile.portal.show](/docs/kintone/js-api/events/portal-display-events/onload-event/#onload-event-mobile) |

#### Space Display Events {#space-display-events}

| Triggered Timing | Desktop | Mobile |
| :-- | :-- | :-- |
| Onload Event | [space.portal.show](/docs/kintone/js-api/events/space-display-events/onload-event/#onload-event-desktop) | [mobile.space.portal.show](/docs/kintone/js-api/events/space-display-events/onload-event/#onload-event-mobile)  |

### Event Handling {#event-handling}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Register Event Handlers | [kintone.events.on()](/docs/kintone/js-api/events/event-handling/#register-event-handlers) | [kintone.events.on()](/docs/kintone/js-api/events/event-handling/#register-event-handlers) |
| Delete a Handler | [kintone.events.off()](/docs/kintone/js-api/events/event-handling/#remove-event-handlers) | [kintone.events.off()](/docs/kintone/js-api/events/event-handling/#remove-event-handlers) |

### API Requests {#api-requests}

#### Internal API Requests {#internal-api-requests}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Kintone REST API Request | [kintone.api()](/docs/kintone/js-api/api/kintone-rest-api-request/) | [kintone.api()](/docs/kintone/js-api/api/kintone-rest-api-request/) |
| Get URL | [kintone.api.url()](/docs/kintone/js-api/api/get-url/) | [kintone.api.url()](/docs/kintone/js-api/api/get-url/) |
| Get URL with Query | [kintone.api.urlForGet()](/docs/kintone/js-api/api/get-url-including-query/) | [kintone.api.urlForGet()](/docs/kintone/js-api/api/get-url-including-query/) |
| Get CSRF Token | [kintone.getRequestToken()](/docs/kintone/js-api/api/get-csrf-token/) | [kintone.getRequestToken()](/docs/kintone/js-api/api/get-csrf-token/) |
| Get Concurrency Limit | [kintone.api.getConcurrencyLimit()](/docs/kintone/js-api/api/get-concurrency-limit/) | [kintone.api.getConcurrencyLimit()](/docs/kintone/js-api/api/get-concurrency-limit/) |

#### External API Requests {#external-api-requests}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Proxy Request | [kintone.proxy()](/docs/kintone/js-api/proxy/kintone-proxy/) | [kintone.proxy()](/docs/kintone/js-api/proxy/kintone-proxy/)  |
| Proxy File Upload | [kintone.proxy.upload()](/docs/kintone/js-api/proxy/kintone-proxy-upload/) | [kintone.proxy.upload()](/docs/kintone/js-api/proxy/kintone-proxy-upload/)  |

### Get/Set Data {#get-set-data}

#### Records {#records}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get Record ID | [kintone.app.record.getId()](/docs/kintone/js-api/record/get-record-id/) | [kintone.mobile.app.record.getId()](/docs/kintone/js-api/record/get-record-id/) |
| Get Record Details | [kintone.app.record.get()](/docs/kintone/js-api/record/get-record/) | [kintone.mobile.app.record.get()](/docs/kintone/js-api/record/get-record/) |
| Set Record Value | [kintone.app.record.set()](/docs/kintone/js-api/record/set-record-value/) | [kintone.mobile.app.record.set()](/docs/kintone/js-api/record/set-record-value/) |
| Get User's Record Permissions | [kintone.app.record.getPermissions()](/docs/kintone/js-api/record/get-record-permissions) | [kintone.app.record.getPermissions()](/docs/kintone/js-api/record/get-record-permissions) |
| Get User's Record Field Permissions | [kintone.app.record.getFieldPermissions()](/docs/kintone/js-api/record/get-record-field-permissions) | [kintone.app.record.getFieldPermissions()](/docs/kintone/js-api/record/get-record-field-permissions) |
| Get Record Status History | [kintone.app.record.getStatusHistory()](/docs/kintone/js-api/record/get-status-history) | [kintone.app.record.getStatusHistory()](/docs/kintone/js-api/record/get-status-history) |
| Get Available App Actions | [kintone.app.record.getActions()](/docs/kintone/js-api/record/get-record-actions) | [kintone.app.record.getActions()](/docs/kintone/js-api/record/get-record-actions) |

#### Apps {#apps}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get App | [kintone.app.get()](/docs/kintone/js-api/app/get-app) | [kintone.app.get()](/docs/kintone/js-api/app/get-app) |
| Get App ID | [kintone.app.getId()](/docs/kintone/js-api/app/get-app-id/) | [kintone.mobile.app.getId()](/docs/kintone/js-api/app/get-app-id/) |
| Get Form Fields | [kintone.app.getFormFields()](/docs/kintone/js-api/app/get-form-fields/) | [kintone.app.getFormFields()](/docs/kintone/js-api/app/get-form-fields/) |
| Get Form Layout | [kintone.app.getFormLayout()](/docs/kintone/js-api/app/get-form-layout/) | [kintone.app.getFormLayout()](/docs/kintone/js-api/app/get-form-layout/) |
| Check App Test Environment | [kintone.app.isTestEnvironment()](/docs/kintone/js-api/app/is-test-environment/) | [kintone.app.isTestEnvironment()](/docs/kintone/js-api/app/is-test-environment/) |
| Check App Maintenance Mode | [kintone.app.isMaintenanceMode()](/docs/kintone/js-api/app/is-maintenance-mode/) | [kintone.app.isMaintenanceMode()](/docs/kintone/js-api/app/is-maintenance-mode/) |
| Toggle App Description | [kintone.app.showDescription(state)](/docs/kintone/js-api/app/show-or-hide-app-description/) |  |
| Get App Icon URLs | [kintone.app.getIcons()](/docs/kintone/js-api/app/get-app-icon-urls) | [kintone.app.getIcons()](/docs/kintone/js-api/app/get-app-icon-urls) |
| Get Record List Field Elements | [kintone.app.getFieldElements(fieldCode)](/docs/kintone/js-api/app/get-record-list-field-elements/) | [kintone.mobile.app.getFieldElements(fieldCode)](/docs/kintone/js-api/app/get-record-list-field-elements/) |
| Get Record List Header Menu Element | [kintone.app.getHeaderMenuSpaceElement()](/docs/kintone/js-api/app/get-record-list-header-menu-element/) |  |
| Get Record List Header Element | [kintone.app.getHeaderSpaceElement()](/docs/kintone/js-api/app/get-record-list-header-element/) |  |
| Get View Settings | [kintone.app.getView()](/docs/kintone/js-api/app/get-record-list-view/) | [kintone.app.getView()](/docs/kintone/js-api/app/get-record-list-view/) |
| Get List of Views | [kintone.app.getViews()](/docs/kintone/js-api/app/get-record-list-views/) | [kintone.app.getViews()](/docs/kintone/js-api/app/get-record-list-views/) |
| Get Record List Query | [kintone.app.getQueryCondition()](/docs/kintone/js-api/app/get-record-list-query/) | [kintone.mobile.app.getQueryCondition()](/docs/kintone/js-api/app/get-record-list-query/) |
| Get Record List Query (with order by, limit, offset) | [kintone.app.getQuery()](/docs/kintone/js-api/app/get-record-list-query-with-order-by-limit-offset/) | [kintone.mobile.app.getQuery()](/docs/kintone/js-api/app/get-record-list-query-with-order-by-limit-offset/) |
| Get Mobile Header Element |  | [kintone.mobile.app.getHeaderSpaceElement()](/docs/kintone/js-api/app/get-mobile-header-element/) |
| Get Lookup Target | [kintone.app.getLookupTargetAppId()](/docs/kintone/js-api/app/get-lookup-target/) | [kintone.mobile.app.getLookupTargetAppId()](/docs/kintone/js-api/app/get-lookup-target/) |
| Get Related Records Target | [kintone.app.getRelatedRecordsTargetAppId()](/docs/kintone/js-api/app/get-related-records-target/) | [kintone.app.getRelatedRecordsTargetAppId()](/docs/kintone/js-api/app/get-related-records-target/) |
| Get Process Management Settings | [kintone.app.getStatus()](/docs/kintone/js-api/app/get-status) |[kintone.app.getStatus()](/docs/kintone/js-api/app/get-status)|
| Get Available Actions | [kintone.app.record.getStatusActions()](/docs/kintone/js-api/app/get-status-actions) | [kintone.app.record.getStatusActions()](/docs/kintone/js-api/app/get-status-actions) |
| Get Assignees | [kintone.app.record.getAssignees()](/docs/kintone/js-api/app/get-status-assignees) | [kintone.app.record.getAssignees()](/docs/kintone/js-api/app/get-status-assignees) |
| Get Categories | [kintone.app.getCategories()](/docs/kintone/js-api/app/get-categories) | [kintone.app.getCategories()](/docs/kintone/js-api/app/get-categories) |
| Get User's App Permissions | [kintone.app.getPermissions()](/docs/kintone/js-api/app/get-app-permissions) | [kintone.app.getPermissions()](/docs/kintone/js-api/app/get-app-permissions) |

### Space {#space}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get Space Information | [kintone.space.get()](/docs/kintone/js-api/space/get-space) | [kintone.space.get()](/docs/kintone/js-api/space/get-space) |
| Get User's Space Permissions | [kintone.space.getPermissions()](/docs/kintone/js-api/space/get-space-permission) | [kintone.space.getPermissions()](/docs/kintone/js-api/space/get-space-permission) |

### System {#system}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get Available Features | [kintone.system.getAvailableFeatures()](/docs/kintone/js-api/system/get-available-features) | [kintone.system.getAvailableFeatures()](/docs/kintone/js-api/system/get-available-features) |
| Get System Permissions | [kintone.system.getPermissions()](/docs/kintone/js-api/system/get-system-permissions) | [kintone.system.getPermissions()](/docs/kintone/js-api/system/get-system-permissions) |

### License {#license}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Check Trial Mode | [kintone.license.isTrial()](/docs/kintone/js-api/license/is-trial) | [kintone.license.isTrial()](/docs/kintone/js-api/license/is-trial) |

### General {#general}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get Logged-in User | [kintone.getLoginUser()](/docs/kintone/js-api/kintone/get-login-user/) | [kintone.getLoginUser()](/docs/kintone/js-api/kintone/get-login-user/) |
| Get User Custom Fields | [kintone.user.getCustomFields()](/docs/kintone/js-api/kintone/get-custom-field) | [kintone.user.getCustomFields()](/docs/kintone/js-api/kintone/get-custom-field) |
| Get User Groups | [kintone.user.getGroups()](/docs/kintone/js-api/kintone/get-groups) | [kintone.user.getGroups()](/docs/kintone/js-api/kintone/get-groups) |
| Get User Departments | [kintone.user.getOrganizations()](/docs/kintone/js-api/kintone/get-organizations) | [kintone.user.getOrganizations()](/docs/kintone/js-api/kintone/get-organizations) |
| Get Page Type | [kintone.user.getPageType()](/docs/kintone/js-api/kintone/get-page-type) | [kintone.user.getPageType()](/docs/kintone/js-api/kintone/get-page-type) |
| Get User Icons | [kintone.user.getIcons()](/docs/kintone/js-api/kintone/get-user-icons) | [kintone.user.getIcons()](/docs/kintone/js-api/kintone/get-user-icons) |
| Get Design | [kintone.getUiVersion()](/docs/kintone/js-api/kintone/get-design/) | [kintone.getUiVersion()](/docs/kintone/js-api/kintone/get-design/) |
| Get Available Services | [kintone.getAvailableServices()](/docs/kintone/js-api/kintone/get-available-services) | [kintone.getAvailableServices()](/docs/kintone/js-api/kintone/get-available-services) |
| Get Domain Information | [kintone.getDomain()](/docs/kintone/js-api/kintone/get-design) | [kintone.getDomain()](/docs/kintone/js-api/kintone/get-design) |
| Get Available API Types | [kintone.getAvailableApiTypes()](/docs/kintone/js-api/kintone/get-available-api-types) | [kintone.getAvailableApiTypes()](/docs/kintone/js-api/kintone/get-available-api-types) |
| Check Client Certificate | [kintone.isAccessWithClientCertificateAuthentication()](/docs/kintone/js-api/kintone/is-access-with-client-certificate-authentication) | [kintone.isAccessWithClientCertificateAuthentication()](/docs/kintone/js-api/kintone/is-access-with-client-certificate-authentication) |
| Check Mobile App | [kintone.isMobileApp()](/docs/kintone/js-api/kintone/is-mobile-app) | [kintone.isMobileApp()](/docs/kintone/js-api/kintone/is-mobile-app) |
| Check Mobile Page | [kintone.isMobilePage()](/docs/kintone/js-api/kintone/is-mobile-page) | [kintone.isMobilePage()](/docs/kintone/js-api/kintone/is-mobile-page) |
| Get User Preference | [kintone.getUserPreference()](/docs/kintone/js-api/kintone/get-user-preference) | [kintone.getUserPreference()](/docs/kintone/js-api/kintone/get-user-preference)  |
| Check User & System Administrator | [kintone.isUsersAndSystemAdministrator()](/docs/kintone/js-api/kintone/is-user-and-system-administrator) | [kintone.isUsersAndSystemAdministrator()](/docs/kintone/js-api/kintone/is-user-and-system-administrator) |
| Check Revamped UI | [kintone.isRevampedUI()](/docs/kintone/js-api/kintone/is-revamped-ui) | [kintone.isRevampedUI()](/docs/kintone/js-api/kintone/is-revamped-ui) |
| Display Confirmation Dialog | [kintone.showConfirmDialog()](/docs/kintone/js-api/kintone/show-confirm-dialog/) |  |
| Create Dialog | [kintone.createDialog()](/docs/kintone/js-api/kintone/create-dialog) |  |
| Display Notification Message | [kintone.showNotification()](/docs/kintone/js-api/kintone/show-notification/) |  |
| Toggle Loading UI | [kintone.showLoading()](/docs/kintone/js-api/kintone/show-loading/) |  |
| Generate page URL | [kintone.buildPageUrl()](/docs/kintone/js-api/kintone/build-page-url/) | [kintone.buildPageUrl()](/docs/kintone/js-api/kintone/build-page-url/) |
| Set Keyboard Shortcuts | [kintone.setKeyboardShortcuts()](/docs/kintone/js-api/kintone/set-keybord-shortcuts/) |  |
| Get Keyboard Shortcuts State | [kintone.getKeyboardShortcuts()](/docs/kintone/js-api/kintone/get-keyboard-shortcuts/) |  |

### Field Visibility {#field-visibility}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Show or Hide Field | [kintone.app.record.setFieldShown()](/docs/kintone/js-api/record/show-or-hide-a-field/) | [kintone.mobile.app.record.setFieldShown()](/docs/kintone/js-api/record/show-or-hide-a-field/) |
| Open Field Group | [kintone.app.record.setGroupFieldOpen()](/docs/kintone/js-api/record/open-field-group/) | [kintone.mobile.app.record.setGroupFieldOpen()](/docs/kintone/js-api/record/open-field-group/)  |
| Check Field Visibility | [kintone.app.record.isFieldVisible()](/docs/kintone/js-api/record/is-field-visible) | [kintone.mobile.app.record.isFieldVisible()](/docs/kintone/js-api/record/is-field-visible) |
| Check Group Field Status | [kintone.app.record.isGroupFieldOpen()](/docs/kintone/js-api/record/is-group-field-open) | [kintone.mobile.app.record.isGroupFieldOpen()](/docs/kintone/js-api/record/is-group-field-open) |

### Show or Hide App UI Elements {#hide-show-elements}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Toggle App Description | [kintone.app.showDescription()](/docs/kintone/js-api/app/show-or-hide-app-description) | |
| Show or Hide New Record Button | [kintone.app.showAddRecordButton()](/docs/kintone/js-api/record/show-or-hide-add-record-button) | [kintone.mobile.app.showAddRecordButton()](/docs/kintone/js-api/record/show-or-hide-add-record-button) |
| Show or Hide App Settings Button | [kintone.app.showAppSettingsButton()](/docs/kintone/js-api/record/show-or-hide-app-settings-button) | |
| Show or Hide Duplicate Record Button | [kintone.app.record.showDuplicateRecordButton()](/docs/kintone/js-api/record/show-or-hide-duplicate-record-button) | |
| Show or Hide Edit Record Button | [kintone.app.record.showEditRecordButton()](/docs/kintone/js-api/record/show-or-hide-edit-record-button) | [kintone.mobile.app.record.showEditRecordButton()](/docs/kintone/js-api/record/show-or-hide-edit-record-button) |
| Show or Hide Filter Button | [kintone.app.showFilterButton()](/docs/kintone/js-api/record/show-or-hide-filter-button) | [kintone.mobile.app.showFilterButton()](/docs/kintone/js-api/record/show-or-hide-filter-button) |
| Show or Hide Graphs Selection | [kintone.app.showViewAndReportSelector()](/docs/kintone/js-api/record/show-or-hide-view-and-report-selector) | [kintone.mobile.app.showReportSelector()](/docs/kintone/js-api/record/show-or-hide-mobile-report-selector) |
| Show or Hide Views Selection | [kintone.app.showViewAndReportSelector()](/docs/kintone/js-api/record/show-or-hide-view-and-report-selector) | [kintone.mobile.app.showViewSelector()](/docs/kintone/js-api/record/show-or-hide-mobile-view-selector) |
| Show or Hide Options Button | [kintone.app.showOptionsButton()](/docs/kintone/js-api/record/show-or-hide-option-button) | [kintone.mobile.app.showOptionsButton()](/docs/kintone/js-api/record/show-or-hide-option-button) |
| Show or Hide Record Navigation Buttons | [kintone.app.record.showPager()](/docs/kintone/js-api/record/show-or-hide-record-nav-button) | [kintone.mobile.app.record.showPager()](/docs/kintone/js-api/record/show-or-hide-record-nav-button) |
| Show or Hide Graph Button | [kintone.app.showReportButton()](/docs/kintone/js-api/record/show-or-hide-report-button) | |
| Toggle Sidebar | [kintone.app.record.showSideBar()](/docs/kintone/js-api/record/show-or-hide-side-bar) | |
| Show or Hide App Action Button | [kintone.app.record.showActionButton()](/docs/kintone/js-api/record/show-or-hide-action-button) |[kintone.mobile.app.record.showActionButton()](/docs/kintone/js-api/record/show-or-hide-action-button) |
| Show or Hide Process Management Action Button | [kintone.app.record.showStatusActionButton()](/docs/kintone/js-api/record/show-or-hide-status-action-button) |[kintone.mobile.app.record.showStatusActionButton()](/docs/kintone/js-api/record/show-or-hide-status-action-button) |

### Get Element Display State {#get-element-display-state}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get App Description Display State | [kintone.app.getDescriptionDisplayState()](/docs/kintone/js-api/app/get-display-state-app-description) |  |
| Get Sidebar Display State | [kintone.app.record.getSideBarDisplayState()](/docs/kintone/js-api/record/get-display-state-side-bar) |  |
| Get New Record Button Display State | [kintone.app.getAddRecordButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-add-record-button) | [kintone.mobile.app.getAddRecordButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-add-record-button) |
| Get Edit Record Button Display State | [kintone.app.record.getEditRecordButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-edit-record-button) | [kintone.mobile.app.record.getEditRecordButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-edit-record-button) |
| Get Duplicate Record Button Display State | [kintone.app.record.getDuplicateRecordButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-duplicate-record-button) |  |
| Get App Settings Button Display State | [kintone.app.getAppSettingsButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-app-settings-button) |  |
| Get Options Button Display State | [kintone.app.getOptionsButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-option-button) | [kintone.mobile.app.getOptionsButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-option-button) |
| Get Record Navigation Buttons Display State | [kintone.app.record.getPagerDisplayState()](/docs/kintone/js-api/record/get-display-state-record-nav-button) | [kintone.mobile.app.record.getPagerDisplayState()](/docs/kintone/js-api/record/get-display-state-record-nav-button) |
| Get Filter Button Display State | [kintone.app.getFilterButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-filter-button) | [kintone.mobile.app.getFilterButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-filter-button) |
| Get Create Graph Button Display State | [kintone.app.getReportButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-report-button) |  |
| Get Graphs Selection Display State | [kintone.app.getViewAndReportSelectorDisplayState()](/docs/kintone/js-api/record/get-display-state-view-and-report-selector) | [kintone.mobile.app.getReportSelectorDisplayState()](/docs/kintone/js-api/record/get-display-state-mobile-report-selector) |
| Get Views Selection Display State | [kintone.app.getViewAndReportSelectorDisplayState()](/docs/kintone/js-api/record/get-display-state-view-and-report-selector) | [kintone.mobile.app.getViewSelectorDisplayState()](/docs/kintone/js-api/record/get-display-state-mobile-view-selector) |
| Get App Action Button Display State | [kintone.app.record.getActionButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-action-button) | [kintone.mobile.app.record.getActionButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-action-button) |
| Get Process Management Action Button Display State | [kintone.app.record.getStatusActionButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-status-action-button) | [kintone.mobile.app.record.getStatusActionButtonDisplayState()](/docs/kintone/js-api/record/get-display-state-status-action-button) |

### Get Elements {#get-elements}

#### Record Details {#get-element-record-detail}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get Record Field Element | [kintone.app.record.getFieldElement()](/docs/kintone/js-api/record/get-record-field-element/) | [kintone.mobile.app.record.getFieldElement()](/docs/kintone/js-api/record/get-record-field-element/) |
| Get Record Header Menu Element | [kintone.app.record.getHeaderMenuSpaceElement()](/docs/kintone/js-api/record/get-record-header-menu-element/) |  |
| Get Mobile Header Element | | [kintone.mobile.app.getHeaderSpaceElement()](/docs/kintone/js-api/app/get-mobile-header-element) |
| Get Space Element | [kintone.app.record.getSpaceElement()](/docs/kintone/js-api/record/get-space-element/) | [kintone.mobile.app.record.getSpaceElement()](/docs/kintone/js-api/record/get-space-element/) |

#### Record List {#get-element-record-list}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get Record List Field Elements | [kintone.app.getFieldElements()](/docs/kintone/js-api/app/get-record-list-field-elements/) | [kintone.mobile.app.getFieldElements()](/docs/kintone/js-api/app/get-record-list-field-elements/) |
| Get Record List Header Menu Element | [kintone.app.getHeaderMenuSpaceElement()](/docs/kintone/js-api/app/get-record-list-header-menu-element/) |  |
| Get Record List Header Element | [kintone.app.getHeaderSpaceElement()](/docs/kintone/js-api/app/get-record-list-header-element/) |  |
| Get Mobile Header Element | | [kintone.mobile.app.getHeaderSpaceElement()](/docs/kintone/js-api/app/get-mobile-header-element/) |

#### Portal {#get-elements-portal}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get Portal | [kintone.portal.getContentSpaceElement()](/docs/kintone/js-api/portal/get-space-element/) | [kintone.mobile.portal.getContentSpaceElement()](/docs/kintone/js-api/portal/get-space-element/) |

#### Space {#get-elements-space}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get Space Element | [kintone.space.portal.getContentSpaceElement()](/docs/kintone/js-api/space/get-space-element/) | [kintone.mobile.space.portal.getContentSpaceElement()](/docs/kintone/js-api/space/get-space-element/) |

### Plug-in {#get-elements-plug-in}

| API | Desktop | Mobile |
| :-- | :-- | :-- |
| Get Config | [kintone.plugin.app.getConfig()](/docs/kintone/js-api/plugins/get-config/) | [kintone.plugin.app.getConfig()](/docs/kintone/js-api/plugins/get-config/) |
| Set Config | [kintone.plugin.app.setConfig()](/docs/kintone/js-api/plugins/set-config/) |   |
| Proxy Set Config | [kintone.plugin.app.setProxyConfig()](/docs/kintone/js-api/plugins/set-config-for-proxy/) |  |
| Proxy Get Config | [kintone.plugin.app.getProxyConfig()](/docs/kintone/js-api/plugins/get-config-for-proxy/) |  |
| Plug-in Proxy Request | [kintone.plugin.app.proxy()](/docs/kintone/js-api/plugins/kintone-plug-in-proxy/) | [kintone.plugin.app.proxy()](/docs/kintone/js-api/plugins/kintone-plug-in-proxy/) |
| Plug-in Proxy File | [kintone.plugin.app.proxy.upload()](/docs/kintone/js-api/plugins/kintone-plug-in-proxy-upload/) | [kintone.plugin.app.proxy.upload()](/docs/kintone/js-api/plugins/kintone-plug-in-proxy-upload/) |
