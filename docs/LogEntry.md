# GongAPI::LogEntry

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**event_time** | **String** | The time in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC); when log was created. | [optional] 
**impersonator_company_id** | **String** | Gong&#x27;s unique numeric identifier for the impersonating user&#x27;s company id (up to 20 digits), if available. | [optional] 
**impersonator_email_address** | **String** | The email address of the impersonating user, if available. | [optional] 
**impersonator_full_name** | **String** | The full name of the impersonating user, if available. | [optional] 
**impersonator_user_id** | **String** | Gong&#x27;s unique numeric identifier for the impersonating user (up to 20 digits), if available. | [optional] 
**log_record** | **Object** | The list of log fields and associated values. This element will be populated dynamically by the log record, depending on the type of log. | [optional] 
**user_email_address** | **String** | The email address of the user, if available. | [optional] 
**user_full_name** | **String** | The full name of the user, if available. | [optional] 
**user_id** | **String** | Gong&#x27;s unique numeric identifier for the user (up to 20 digits), if available. | [optional] 

