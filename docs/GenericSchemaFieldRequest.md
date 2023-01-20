# GongAPI::GenericSchemaFieldRequest

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**is_deleted** | **BOOLEAN** | \&quot;true\&quot; deletes the field from the schema and its value is removed from all objects. Use with caution. | [optional] 
**label** | **String** | The label is used to display the field | 
**last_modified** | **String** | The last modification timestamp of the field schema. &lt;br&gt;The timestamp should be in the ISO-8601 format without milliseconds e.g., \&quot;2020-12-17T13:45:01Z\&quot; | [optional] 
**name** | **String** | &lt;b&gt;Deprecated&lt;/b&gt;. Please use uniqueName | [optional] 
**ordered_value_list** | **Array&lt;String&gt;** | Required for fields of type PICKLIST. Provides the list of available values for the field | [optional] 
**reference_to** | **String** | Required for field of type REFERENCE. Defines the type of object referred to by this field. Must be one of \&quot;ACCOUNT\&quot;, \&quot;CONTACT\&quot;, \&quot;DEAL\&quot;, \&quot;LEAD\&quot; or \&quot;USER\&quot; | [optional] 
**type** | **String** | The field type (case-sensitive). See the &lt;b&gt;Supported Field Types&lt;/b&gt; table. | 
**unique_name** | **String** | The unique name of the field in the CRM system | 

