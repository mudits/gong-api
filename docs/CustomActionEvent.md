# GongAPI::CustomActionEvent

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**action_name** | **String** | The name of the action like \&quot;Document Viewed\&quot; or \&quot;Presentation Opened\&quot;. | [optional] 
**actor** | [**Actor**](Actor.md) |  | [optional] 
**agent_platform** | **String** | Platform on which the interaction was made | [optional] 
**content_id** | **String** | The id of the content that was viewed in the reporting system. | [optional] 
**content_properties** | [**Array&lt;GenericProperty&gt;**](GenericProperty.md) | A list of additional properties for the content | [optional] 
**content_title** | **String** | Human readable title of the content. | [optional] 
**content_url** | **String** | The url of the content that was viewed in the reporting system. This is the url that is was accessed by the viewer. | [optional] 
**crm_context** | [**Array&lt;CallUploadContext&gt;**](CallUploadContext.md) | A list of references to external systems such as CRM, Telephony System, Case Management, etc. | [optional] 
**event_id** | **String** | The original id of the event as designated in the reporting system. | [optional] 
**event_info_url** | **String** | The link to a page that presents additional information about this event. | [optional] 
**event_properties** | [**Array&lt;GenericProperty&gt;**](GenericProperty.md) | A list of additional properties for the event | [optional] 
**event_timestamp** | **String** | The date and time when the event happened in the ISO-8601 format (e.g., &#x27;2021-08-01T02:30:00+05:00&#x27; or &#x27;2021-08-01T08:00:00Z&#x27;, where Z stands for UTC); | 
**mobile_app_id** | **String** | The application identification string in case of interaction via mobile application (bundle identifier or package name). | [optional] 
**reporting_system** | **String** | The unique identifier of the reporting system. It is the same value in all events originating from the same system. | 
**user_agent** | **String** | \&quot;User-Agent\&quot; header value for browser based interaction | [optional] 
**workspace_id** | **String** | Optional workspace identifier. If specified, the event will be placed into this workspace, otherwise, the default algorithm for workspace placement will be applied. | [optional] 

