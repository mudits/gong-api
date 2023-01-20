# GongAPI::ContentSelector

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**context** | **String** | If &#x27;Basic&#x27;, add links to external systems (context objects) such as CRM, Telephony System, Case Management. If &#x27;Extended&#x27; include also data (context fields) for these links. Default value &#x27;None&#x27; | [optional] 
**context_timing** | **Array&lt;String&gt;** | Timing for the context data. The field is optional and can contain either \&quot;Now\&quot; or \&quot;TimeOfCall\&quot; or both. The default value is [\&quot;Now\&quot;]. Can be provided only when the context field is set to &#x27;Extended&#x27; | [optional] 
**exposed_fields** | [**ExposedFields**](ExposedFields.md) |  | [optional] 

