# GongAPI::CRMApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_generic_crm_integration_using_delete**](CRMApi.md#delete_generic_crm_integration_using_delete) | **DELETE** /v2/crm/integration/delete | Delete a Generic CRM integration (/v2/crm/integration/delete)
[**get_crm_objects_using_get**](CRMApi.md#get_crm_objects_using_get) | **GET** /v2/crm/object/list | Get CRM objects (/v2/crm/object/list)
[**get_request_status_using_get**](CRMApi.md#get_request_status_using_get) | **GET** /v2/crm/request-status | Get Request Status (/v2/crm/request-status)
[**list_crm_schema_fields_using_get**](CRMApi.md#list_crm_schema_fields_using_get) | **GET** /v2/crm/object/schema/list | List Schema Fields (/v2/crm/object/schema/list)
[**list_generic_crm_integration_using_get**](CRMApi.md#list_generic_crm_integration_using_get) | **GET** /v2/crm/integration/list | Get Generic CRM integration details (/v2/crm/integration/list)
[**map_crm_users_using_post**](CRMApi.md#map_crm_users_using_post) | **POST** /v2/crm/map/users | Map Users (Deprecated)
[**register_generic_crm_integration_using_put**](CRMApi.md#register_generic_crm_integration_using_put) | **PUT** /v2/crm/integration/new | Register a Generic CRM integration (/v2/crm/integration/new)
[**upload_crm_data_using_post**](CRMApi.md#upload_crm_data_using_post) | **POST** /v2/crm/object/entities | Upload CRM objects (/v2/crm/object/entities)
[**upload_crm_schema_field_using_post**](CRMApi.md#upload_crm_schema_field_using_post) | **POST** /v2/crm/object/schema | Upload Object Schema (/v2/crm/object/schema)
[**upload_stages_using_post**](CRMApi.md#upload_stages_using_post) | **POST** /v2/crm/stages | Upload Stages (Deprecated)

# **delete_generic_crm_integration_using_delete**
> AsyncProcessingResponse delete_generic_crm_integration_using_delete(client_request_id, integration_id)

Delete a Generic CRM integration (/v2/crm/integration/delete)

<style>.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}</style><p>Deletes a Generic CRM integration and all its associated crm objects (Accounts, Contacts, Deals, Leads, and Users).</p><p>This API is asynchronous. Call \"/request-status\" API with the clientRequestId sent to this API to track progress of the delete request:<br>Status DONE indicates that the integration and all its associated crm objects have been successfully deleted. Calls associations may take up to 24 hours to be deleted.</p><h3>Example</h3><h4>Request</h4><code>DELETE https://api.gong.io/v2/crm/integration/delete?clientRequestId=1234&integrationId=6286478263646</code><p>When accessed using a bearer token, this endpoint requires the scope 'api:crm:integration:delete'.</p>

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CRMApi.new
client_request_id = 'client_request_id_example' # String | A unique identifier sent by you to allow troubleshooting requests. Valid characters for this field are letters, numbers, dashes and underscores.
integration_id = 789 # Integer | Integration ID generated when creating the integration


begin
  #Delete a Generic CRM integration (/v2/crm/integration/delete)
  result = api_instance.delete_generic_crm_integration_using_delete(client_request_id, integration_id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CRMApi->delete_generic_crm_integration_using_delete: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **client_request_id** | **String**| A unique identifier sent by you to allow troubleshooting requests. Valid characters for this field are letters, numbers, dashes and underscores. | 
 **integration_id** | **Integer**| Integration ID generated when creating the integration | 

### Return type

[**AsyncProcessingResponse**](AsyncProcessingResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_crm_objects_using_get**
> GetGenericCrmObjectsResponse get_crm_objects_using_get(bodyintegration_idobject_type)

Get CRM objects (/v2/crm/object/list)

<style>.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}</style><p>This API is intended to be used in <b>development phase only</b>, to manually verify that objects are uploaded and processed correctly in Gong.</p><p>Returns a JSON object where each key is the object crm id and the corresponding value is a nested JSON object representing the CRM object fields. Each key in the nested JSON is the field name and the corresponding value is the field value.</p><p>The objects are fetched from the Gong main DB. If the object is not found, the JSON’s value will be null.</p><p>The request body contains an array of objects ids.</p><p>The request is limited to 100 objects. If more than 100 objects are requested only the first 100 are returned.</p><p>When accessed using a bearer token, this endpoint requires the scope 'api:crm:get-objects'.</p>

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CRMApi.new
body = ['body_example'] # Array<String> | Requested objects crm ids
integration_id = 789 # Integer | Integration ID generated when creating the integration
object_type = 'object_type_example' # String | Requested objects type


begin
  #Get CRM objects (/v2/crm/object/list)
  result = api_instance.get_crm_objects_using_get(bodyintegration_idobject_type)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CRMApi->get_crm_objects_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**Array&lt;String&gt;**](String.md)| Requested objects crm ids | 
 **integration_id** | **Integer**| Integration ID generated when creating the integration | 
 **object_type** | **String**| Requested objects type | 

### Return type

[**GetGenericCrmObjectsResponse**](GetGenericCrmObjectsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json



# **get_request_status_using_get**
> RequestStatusResponse get_request_status_using_get(client_request_id, integration_id)

Get Request Status (/v2/crm/request-status)

<style>.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}</style><p>Returns the current status of the request for \"/map/users\", \"/object/entities\" or \"/integration/delete\" API.</p><p>When accessed using a bearer token, this endpoint requires the scope 'api:crm:upload'.</p><h3>Status Codes</h3><ul>    <li><span class='public-api-parameter'>PENDING</span> - File is pending parsing</li>    <li><span class='public-api-note'>IN_PROGRESS</span> - File is being parsed</li>    <li><span class='public-api-info'>DONE</span> - All objects in the file were successfully parsed</li>    <li><span class='public-api-critical'>FAILED</span> - Failed to parse some objects in the file or on a general error when the file was being processed</li></ul><h3>Status Indication</h3><ul>    <li>For \"/object/entities\" API, status <span class='public-api-info'>DONE</span> indicates that all objects in the LDJSON file were successfully parsed and stored in raw storage.<br>        Note that it can take up to 1 hour from the time the LDJSON file was uploaded using the \"/object/entities\" API until deals are fully processed and available to the end user on the Deals Board.    </li>    <li>For \"/map/users\" API, status <span class='public-api-info'>DONE</span> indicates that the mapping was successfully created and is available in Gong for the processing of other objects.</li>    <li><span class='public-api-critical'>FAILED</span>:        <ul>            <li>If you receive a <span class='public-api-critical'>FAILED</span> status with a specific error list there are errors you need to address in the object:                <ul>                    <li>Fix the objects' JSON.</li>                    <li>Resend the entire LDJSON file to \"/object/entities\" or \"/map/users\" API.<br>                        Note that The returned errors list is <b>limited to the first 20 errors</b>. To make sure you have corrected all the possible errors you need to upload the entire file repeatedly until you receive a <span class='public-api-info'>DONE</span> status.                    </li>                </ul>            </li>            <li>If you received a <span class='public-api-critical'>FAILED</span> status with a single error in the form of<br>                {\"line\":0,\"description\":\".....\"} this indicates a general processing error:                <ul>                    <li>Fix the LDJSON file according to the error message.</li>                    <li>Upload the entire LDJSON file again.</li>                </ul>            </li>        </ul>    </li></ul>

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CRMApi.new
client_request_id = 'client_request_id_example' # String | <span style='background: rgba(9,30,66,0.08)'>clientRequestId</span> sent to \"/map/users\", \"/object/entities\" or \"/integration/delete\" API
integration_id = 789 # Integer | Integration ID generated when creating the integration


begin
  #Get Request Status (/v2/crm/request-status)
  result = api_instance.get_request_status_using_get(client_request_id, integration_id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CRMApi->get_request_status_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **client_request_id** | **String**| &lt;span style&#x3D;&#x27;background: rgba(9,30,66,0.08)&#x27;&gt;clientRequestId&lt;/span&gt; sent to \&quot;/map/users\&quot;, \&quot;/object/entities\&quot; or \&quot;/integration/delete\&quot; API | 
 **integration_id** | **Integer**| Integration ID generated when creating the integration | 

### Return type

[**RequestStatusResponse**](RequestStatusResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **list_crm_schema_fields_using_get**
> ListSelectedFieldsResponse list_crm_schema_fields_using_get(integration_id, object_type)

List Schema Fields (/v2/crm/object/schema/list)

<style>.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}</style><p>Retrieves a list of the object schema fields.</p><p>When accessed using a bearer token, this endpoint requires the scope 'api:crm:schema'.</p><h3>Example</h3><h4>Request</h4><code>GET https://api.gong.io/v2/crm/object/schema/list?integrationId=6286478263646&objectType=ACCOUNT</code><h4>Response</h4><code>{    \"requestId\": \"afjkzqkqglog7ueki5\",    \"selectedFields\": {        \"ACCOUNT\": [            {                \"name\": \"accountTypePicklist\",                \"label\": \"Account Type\",                \"type\": \"PICKLIST\",                \"lastModified\": null,                \"isDeleted\": false,                \"referenceTo\": null,                \"orderedValueList\": null            },            {                \"name\": \"accountTypePicklist2\",                \"label\": \"Account Type2\",                \"type\": \"PICKLIST\",                \"lastModified\": null,                \"isDeleted\": false,                \"referenceTo\": null,                \"orderedValueList\": null            },            {                \"name\": \"fooBar\",                \"label\": \"Foo Bar\",                \"type\": \"STRING\",                \"lastModified\": null,                \"isDeleted\": false,                \"referenceTo\": null,                \"orderedValueList\": null            }        ]    }}</code>

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CRMApi.new
integration_id = 789 # Integer | Integration ID generated when creating the integration
object_type = 'object_type_example' # String | Type of object to retrieve the schema fields for (case-sensitive). <br>Omitting this parameter returns the schema for all object types.


begin
  #List Schema Fields (/v2/crm/object/schema/list)
  result = api_instance.list_crm_schema_fields_using_get(integration_id, object_type)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CRMApi->list_crm_schema_fields_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **integration_id** | **Integer**| Integration ID generated when creating the integration | 
 **object_type** | **String**| Type of object to retrieve the schema fields for (case-sensitive). &lt;br&gt;Omitting this parameter returns the schema for all object types. | 

### Return type

[**ListSelectedFieldsResponse**](ListSelectedFieldsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **list_generic_crm_integration_using_get**
> ListGenericCrmIntegrationsResponse list_generic_crm_integration_using_get

Get Generic CRM integration details (/v2/crm/integration/list)

<style>.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}</style><p>Returns a list of all active Generic CRM integrations of the company. Only integrations created with 'Register a Generic CRM integration' API are returned.<br>Only one active integration is currently supported.</p><p>When accessed using a bearer token, this endpoint requires the scope 'api:crm:integrations:read'.</p>

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CRMApi.new

begin
  #Get Generic CRM integration details (/v2/crm/integration/list)
  result = api_instance.list_generic_crm_integration_using_get
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CRMApi->list_generic_crm_integration_using_get: #{e}"
end
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**ListGenericCrmIntegrationsResponse**](ListGenericCrmIntegrationsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **map_crm_users_using_post**
> AsyncProcessingResponse map_crm_users_using_post(opts)

Map Users (Deprecated)

<style>.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}</style><p>This API is <b>Deprecated</b>. Please use \"/object/entities?objectType=BUSINESS_USER\" API instead.</p><p>Gong associates users with the CRM <b>User</b> entity. Mapping users accurately is essential for Gong to connect users with all their associated objects in the CRM.</p><p>This API creates a mapping in Gong between the user ID in the CRM system and the user ID in Gong.</p><br><div class='public-api-important'><b>Important:</b><p>User mapping is important to ensure deals are processed in Gong correctly. Each uploaded deal contains an ownerId field, which contains a user ID from the CRM system.<br><b>Gong only processes a deal if this user ID is mapped to a user in Gong who is set to record or import calls.</b></p><p>Each request to this API must include the complete list of users from the CRM system.</p></div><p>If a user mapping is sent after a deal is uploaded:</p><ol>    <li>Gong retroactively searches for deals whose ownerId matches the user ID mapping.</li>    <li>Gong starts to reprocess those matched deals from raw storage into Gong’s main database.</li></ol><p>Gong matches the user from the uploaded JSON to a user in Gong based on the email address.</p><div class='public-api-info'><p>The user mapping will not be created when:</p><ul>    <li>There is no user in Gong with the supplied email address</li>    <li>Mapping already exists for the supplied email address</li></ul></div><p>To update an existing mapping:</p><ol>    <li>Delete the existing mapping by sending an existing mapping with isDeleted=true.</li>    <li>In a separate request send a new mapping for the email address.</li></ol><p>The request body is a file in LDJSON format, meaning the file should contain JSON objects - where each JSON object is on a separate line and represents a single user from the CRM system.</p><p><b>Request Body Specifications:</b></p><ul>    <li>Content-Type should be multipart/form-data</li>    <li>Maximum payload size: 200 megabytes</li>    <li>The request body should include one parameter named \"<b>dataFile</b>\" which contains the LDJSON file.</li></ul><h3>Request parameters (QUERY-STRING parameters)</h3><table>    <thead>        <tr>            <th>Name</th>            <th>Description</th>            <th>Data Type</th>            <th>Mandatory</th>        </tr>    </thead>    <tbody>        <tr>            <td><span class='public-api-parameter'>clientRequestId</span></td>            <td>A unique identifier sent by you to enable troubleshooting communication.<br>            Gong uses this identifier to prevent repeated attempts to upload the same users list.<br>            Valid characters for this field: Letters, numbers, dashes, and underscores.            </td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>integrationId</span></td>            <td>Integration ID generated when creating the integration</td>            <td>long</td>            <td>Y</td>        </tr>    </tbody></table><p>User JSON object requires the following fields:</p><table>    <thead>        <tr>            <th>Name</th>            <th>Description</th>            <th>Data Type</th>            <th>Mandatory</th>        </tr>    </thead>    <tbody>        <tr>            <td><span class='public-api-parameter'>crmUserId</span></td>            <td>User ID in the CRM system</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>emailAddress</span></td>            <td>Must match an email address of a user in Gong. Not mandatory when isDeleted = true.</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>isDeleted</span></td>            <td>\"true\" deletes the user mapping. Default = \"false\"</td>            <td>boolean</td>            <td>N</td>        </tr>    </tbody></table><h3>Response</h3><code>201 Created</code><table>    <thead>        <tr>            <th>Name</th>            <th>Data Type</th>            <th>Description</th>        </tr>    </thead>    <tbody>        <tr>            <td><span class='public-api-parameter'>clientRequestId</span></td>            <td>string</td>            <td>the <span class='public-api-parameter'>clientRequestId</span> sent in the request</td>        </tr>        <tr>            <td><span class='public-api-parameter'>requestId</span></td>            <td>string</td>            <td>A Gong request reference Id, generated for this request</td>        </tr>    </tbody></table><div class='public-api-important'><p><b>Important:</b> The users mapping API is asynchronous. A 201 response only indicates that the file successfully uploaded to Gong and is pending processing. Use the <span class='public-api-parameter'>clientRequestId</span> to troubleshoot failed requests and watch the request status using \"/request-status\" API.</p></div><h3>Error Codes</h3>400 - Malformed request<br>401 - Access denied<br>409 Conflict - clientRequestId already exists<br>429 - API request limit exceeded<br>500 - Internal Server Error<p>When accessed using a bearer token, this endpoint requires the scope 'api:crm:upload'.</p><h3>Example</h3><h4>Request</h4><code>POST https://api.gong.io/v2/crm/map/users?clientRequestId=1234&integrationId=6286478263646</code><br><br><code>{\"crmUserId\": \"2356ddfwe32\", \"emailAddress\": \"john.doe@acme.com\"}<br>{\"crmUserId\": \"67534ghf745\", \"isDeleted\": true} // remove user mapping for user 67534ghf745</code>

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CRMApi.new
opts = { 
  data_file: 'data_file_example' # String | 
}

begin
  #Map Users (Deprecated)
  result = api_instance.map_crm_users_using_post(opts)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CRMApi->map_crm_users_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **data_file** | **String**|  | [optional] 

### Return type

[**AsyncProcessingResponse**](AsyncProcessingResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json



# **register_generic_crm_integration_using_put**
> RegisterGenericCrmResponse register_generic_crm_integration_using_put(body)

Register a Generic CRM integration (/v2/crm/integration/new)

<style>.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}</style><p>Register the CRM application in Gong and use the returned integrationId in future requests to the CRM API to correlate the data with the specific CRM.</p><p>Multiple CRM integrations are not currently supported. To create a new integration, first delete the old one.</p><p>When accessed using a bearer token, this endpoint requires the scope 'api:crm:integration:register'.</p>

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CRMApi.new
body = GongAPI::GenericCrmRegistrationRequest.new # GenericCrmRegistrationRequest | registrationRequest


begin
  #Register a Generic CRM integration (/v2/crm/integration/new)
  result = api_instance.register_generic_crm_integration_using_put(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CRMApi->register_generic_crm_integration_using_put: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**GenericCrmRegistrationRequest**](GenericCrmRegistrationRequest.md)| registrationRequest | 

### Return type

[**RegisterGenericCrmResponse**](RegisterGenericCrmResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **upload_crm_data_using_post**
> AsyncProcessingResponse upload_crm_data_using_post(opts)

Upload CRM objects (/v2/crm/object/entities)

<style>.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}</style><p>Inserts, updates, or deletes a CRM object in Gong.<br>If an existing object with the same id is detected it will be updated, otherwise it will be inserted as a new object.</p><p>The request body is a file in LDJSON format, meaning the file should contain JSON objects, where each JSON object is in a separate line and represents a single CRM object.</p><p>All objects in a single request should be of the same object type. An object cannot be contained more than once in a given list.</p><p><b>Request Body Specifications:</b></p><ul>    <li>Content-Type should be multipart/form-data</li>    <li>Maximum payload size: 200 megabytes</li>    <li>The request body should contain one parameter named \"<b>dataFile</b>\" which holds the LDJSON file</li></ul><div class='public-api-important'><p><b>Important:</b> The list must be sorted by modifiedDate Ascending.</p></div><div class='public-api-info'><p><ul>    <li>On initial upload: Only send the items that weren’t deleted</li>    <li>On subsequent (incremental) uploads: Send all items.</li></ul></p></div><div class='public-api-info'><p>Dates in the uploaded JSON objects are represented in ISO-8601 format without milliseconds (e.g. '2018-02-18T02:30:00-07:00' or '2018-02-18T08:00:00Z', where Z stands for UTC).</p></div><h3>Request parameters (QUERY-STRING parameters)</h3><table>    <thead>        <tr>            <th>Name</th>            <th>Description</th>            <th>Data Type</th>            <th>Mandatory</th>        </tr>    </thead>    <tbody>        <tr>            <td><span class='public-api-parameter'>integrationId</span></td>            <td>Integration ID generated when creating the integration</td>            <td>long</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>objectType</span></td>            <td>Must be one of: \"ACCOUNT\", \"CONTACT\", \"DEAL\", \"LEAD\", \"BUSINESS_USER\", or \"STAGE\" (case-sensitive)</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>clientRequestId</span></td>            <td>A unique identifier sent by you to allow troubleshooting communication.<br>            Gong also uses this identifier to prevent repeated attempts to upload the same object list.<br>            Valid characters for this field are letters, numbers, dashes and underscores.            </td>            <td>string</td>            <td>Y</td>        </tr>    </tbody></table><h3>Response</h3><code>201 Created</code><table>    <thead>        <tr>            <th>Name</th>            <th>Data Type</th>            <th>Description</th>        </tr>    </thead>    <tbody>        <tr>            <td><span class='public-api-parameter'>clientRequestId</span></td>            <td>string</td>            <td>the <span class='public-api-parameter'>clientRequestId</span> sent in the request</td>        </tr>        <tr>            <td><span class='public-api-parameter'>requestId</span></td>            <td>string</td>            <td>A Gong request reference Id, generated for this request</td>        </tr>    </tbody></table><div class='public-api-important'><p><b>Important:</b> The upload objects API is asynchronous. A 201 response only indicates that the file successfully uploaded to Gong and is pending processing. Use the <span class='public-api-parameter'>clientRequestId</span> to troubleshoot failed requests and watch the request status using \"/request-status\" API.</p></div><h3>Error Codes</h3>400 - Malformed request<br>401 - Access denied<br>409 Conflict - clientRequestId already exists<br>429 - API request limit exceeded<br>500 - Internal Server Error<p>When accessed using a bearer token, this endpoint requires the scope 'api:crm:upload'.</p><h2>Common CRM object fields</h2><p>All uploaded CRM objects should contain the following common JSON fields. In addition, each uploaded object should contain mandatory and optional fields as specified below for each object type.</p><table>    <thead>        <tr>            <th>Name</th>            <th>Description</th>            <th>Data Type</th>            <th>Mandatory</th>        </tr>    </thead>    <tbody>        <tr>            <td><span class='public-api-parameter'>objectId</span></td>            <td>Each object must have a unique id field provided by the CRM.</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>modifiedDate</span></td>            <td>The object’s last modification date and time in the CRM in ISO-8601 datetime format, without milliseconds</td>            <td>datetime</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>lastModified</span><b>(Deprecated)</b></td>            <td><b>Deprecated</b>. Please use <span class='public-api-parameter'>modifiedDate</span></td>            <td>datetime</td>            <td>N</td>        </tr>        <tr>            <td><span class='public-api-parameter'>isDeleted</span></td>            <td>\"true\" deletes the object (For objectType=BUSINESS_USER deletes also the user mapping. For objectType=STAGE sets the stage to inactive). Default = \"false\"</td>            <td>boolean</td>            <td>N</td>        </tr>        <tr>            <td><span class='public-api-parameter'>url</span></td>            <td>A full http URL to browse this object in the CRM</td>            <td>string (Qualified URI)</td>            <td>N</td>        </tr>    </tbody></table><h2>Business User Object</h2><p>Gong associates users with the CRM <b>User</b> entity. Mapping users accurately is essential for Gong to connect users with all their associated objects in the CRM.</p><p>Uploading user objects via this API creates a mapping in Gong between the user ID in the CRM system and the user ID in Gong.</p><br><div class='public-api-important'>    <b>Important:</b>    <p>User mapping is important to ensure deals are processed in Gong correctly. Each uploaded deal contains an ownerId field, which contains a user ID from the CRM system.<br>        <b>Gong only processes a deal if this user ID is mapped to a user in Gong who is set to record or import calls.</b>    </p>    <p>On initial upload send the complete list of users from the CRM system. On incremental upload send only users that have changed.</p></div><p>If a user is uploaded after a deal is uploaded:</p><ol>    <li>Gong retroactively searches for deals whose ownerId matches the user ID mapping.</li>    <li>Gong starts to reprocess those matched deals from raw storage into Gong’s main database.</li></ol><p>Gong matches the user from the uploaded JSON to a user in Gong based on the email address.</p><div class='public-api-info'>    <p>The user mapping will not be created when:</p>    <ul>        <li>There is no user in Gong with the supplied email address</li>        <li>Mapping already exists for the supplied email address</li>    </ul></div><p>To update an existing mapping:</p><ol>    <li>Delete the existing mapping by sending the user with isDeleted=true.</li>    <li>In a separate request send the user with isDeleted=false and a new email address, or send a different user for the same email address.</li></ol><p>Business User JSON object requires the following fields:</p><table>    <thead>    <tr>        <th>Name</th>        <th>Description</th>        <th>Data Type</th>        <th>Mandatory</th>    </tr>    </thead>    <tbody>    <tr>        <td><span class='public-api-parameter'>emailAddress</span></td>        <td>Must match an email address of a user in Gong. Not mandatory when isDeleted = true.</td>        <td>string</td>        <td>Y</td>    </tr>    </tbody></table><h3>Example</h3><h4>Request</h4><code>POST https://api.gong.io/v2/crm/object/entities?clientRequestId=1234&integrationId=6286478263646&objectType=BUSINESS_USER</code><br><br><code>    {\"objectId\": \"user1_Id_In_The_CRM\", \"emailAddress\": \"john.doe@acme.com\", \"modifiedDate\": \"2019-01-03T23:45:57+01:00\"}<br>    {\"objectId\": \"user2_Id_In_The_CRM\", \"isDeleted\": true, \"emailAddress\": \"john.taylor@acme.com\", \"modifiedDate\": \"2019-01-03T23:45:57+01:00\"} // remove user mapping for user user2_Id_In_The_CRM</code><h2>Stage Object</h2><p>Update the list of stages from the CRM system.</p><p>Stages must be uploaded via this API before you upload Deal objects. When you upload your Deal object, make sure that the stage field matches one of the stages you’ve uploaded using this API.</p><div class='public-api-info'>    <p>The upload stages request should only be sent after:</p>    <ul>        <li>You have created a new integration.</li>        <li>There are any changes to the list of stages in the CRM. You can also send a stages update request before any request to the '/object/entities' API.</li>    </ul></div><p>Stage JSON object requires the following fields:</p><table>    <thead>    <tr>        <th>Name</th>        <th>Description</th>        <th>Data Type</th>        <th>Mandatory</th>    </tr>    </thead>    <tbody>    <tr>        <td><span class='public-api-parameter'>internalName</span></td>        <td>Unique name or unique identifier that identifies the stage in the CRM.</td>        <td>string</td>        <td>Y</td>    </tr>    <tr>        <td><span class='public-api-parameter'>name</span></td>        <td>Stage name (for display in Gong UI).</td>        <td>string</td>        <td>Y</td>    </tr>    <tr>        <td><span class='public-api-parameter'>isActive</span></td>        <td>Indicates if the stage is active in the CRM.</td>        <td>boolean</td>        <td>Y</td>    </tr>    <tr>        <td><span class='public-api-parameter'>sortOrder</span></td>        <td>The order of the stage in the sales process (starting from 1).</td>        <td>integer</td>        <td>Y</td>    </tr>    </tbody></table><h3>Example</h3><h4>Request</h4><code>POST https://api.gong.io/v2/crm/object/entities?clientRequestId=1234&integrationId=6286478263646&objectType=STAGE</code><br><br><code>    {\"objectId\": \"discovery\", \"modifiedDate\": \"2019-01-03T23:45:57+01:00\", \"internalName\": \"discovery\", \"name\": \"Discovery\", \"isActive\": true, \"sortOrder\": 1}<br>    {\"objectId\": \"won\", \"modifiedDate\": \"2019-01-03T23:45:57+01:00\", \"internalName\": \"won\", \"name\": \"Closed Won\", \"isActive\": true, \"sortOrder\": 5}</code><h2>Account Object</h2><ul>    <li>The Account object represents an active customer in the CRM system.</li>    <li>The Account object is used by Gong to connect activities such as emails and calls to their associated account.</li></ul><p>The Deals page displays all the activities in Gong associated with an account as well as account status, contacts, and insights.</p><div class='public-api-info'><p>Contacts and Deals are associated with accounts, and their processing in Gong requires the associated account.</p><p>In order for Deals to be processed correctly by Gong:<ol>    <li>Upload Accounts.</li>    <li>Wait 60 seconds.</li>    <li>Upload Contacts and Deals.</li></ol></p></div><div class='public-api-critical'><p>When deals are being processed, the account referenced by Deal.accountId must exist in the Gong database.<br>If it does not exist in the database, the deal will not be processed or displayed in the Deals page and other areas throughout Gong.</p></div><p>The Account JSON object includes the following fields:</p><table>    <thead>        <tr>            <th>Name</th>            <th>Description</th>            <th>Data Type</th>            <th>Mandatory</th>        </tr>    </thead>    <tbody>        <tr>            <td><span class='public-api-parameter'>name</span></td>            <td>Account name</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>domains</span></td>            <td>Domain names related to the account</td>            <td>string array</td>            <td>Y</td>        </tr>    </tbody></table><h3>Example</h3><h4>Request</h4><code>POST https://api.gong.io/v2/crm/object/entities?clientRequestId=1234&integrationId=6286478263646&objectType=ACCOUNT</code><br><br><code>{\"objectId\": \"5ybyh6n6n65\", \"modifiedDate\": \"2019-01-03T23:45:57+01:00\", \"url\": \"https://crm.com/accounts/5ybyh6n6n65\", \"name\": \"PBR\", \"domains\": [\"pbr.com\", \"pbr.gov\"], \"type\": \"Investor\"} // account with additional field<br>{\"objectId\": \"gfjhty756th\", \"modifiedDate\": \"2019-01-03T22:45:57Z\", \"name\": \"PBR\", \"domains\": [\"pbr.com\", \"pbr.gov\"], \"isDeleted\": true} // remove account gfjhty756th from Gong</code><h2>Contact Object</h2><ul>    <li>A contact in Gong is a person with contact details associated with the account.</li>    <li>Gong uses a contact to match an activity to the correct account.</li></ul><p>The Contact JSON object includes the following fields:</p><table>    <thead>        <tr>            <th>Name</th>            <th>Description</th>            <th>Data Type</th>            <th>Mandatory</th>        </tr>    </thead>    <tbody>        <tr>            <td><span class='public-api-parameter'>accountId</span></td>            <td>The ID of the contact’s connected account in the CRM</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>emailAddress</span></td>            <td>The contact’s main email address</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>firstName</span></td>            <td>The contact’s first name</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>lastName</span></td>            <td>The contact’s last name</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>title</span></td>            <td>The contact’s title (if available)</td>            <td>string</td>            <td>N</td>        </tr>        <tr>            <td><span class='public-api-parameter'>phoneNumber</span></td>            <td>The contact’s main phone number.<br>            If Gong is configured to import dialer calls the phoneNumber parameter is mandatory.            </td>            <td>string</td>            <td>Y for dialer calls,<br>            N otherwise            </td>        </tr>    </tbody></table><h3>Example</h3><h4>Request</h4><code>POST https://api.gong.io/v2/crm/object/entities?clientRequestId=1234&integrationId=6286478263646&objectType=CONTACT</code><br><br><code>{\"objectId\": \"5zbwd7n5n65\", \"modifiedDate\": \"2019-01-03T23:45:57+01:00\", \"url\": \"https://crm.com/contacts/5zbwd7n5n65\", \"accountId\": \"5ybyh6n6n65\", \"emailAddress\": \"john.smith@acme.com\", \"firstName\": \"john\", \"lastName\": \"smith\", \"phoneNumber\": \"(912) 507-4395\"}</code><h2>Lead Object</h2><ul>    <li>The Lead object represents a potential customer.</li>    <li>Calls and emails are first associated with contacts based on email addresses.</li>    <li>If there is no matching contact, Gong tries to match calls and emails to a lead.</li></ul><p>The Lead JSON object includes the following fields:</p><table>    <thead>        <tr>            <th>Name</th>            <th>Description</th>            <th>Data Type</th>            <th>Mandatory</th>        </tr>    </thead>    <tbody>        <tr>            <td><span class='public-api-parameter'>emailAddress</span></td>            <td>The Lead’s main email address</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>firstName</span></td>            <td>The Lead’s first name</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>lastName</span></td>            <td>The Lead’s last name</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>title</span></td>            <td>The Lead’s title (if available)</td>            <td>string</td>            <td>N</td>        </tr>        <tr>            <td><span class='public-api-parameter'>phoneNumber</span></td>            <td>The Lead’s phone number.<br>            If Gong is configured to import dialer calls the phoneNumber parameter is mandatory.            </td>            <td>string</td>            <td>Y for dialer calls,<br>            N otherwise            </td>        </tr>        <tr>            <td><span class='public-api-parameter'>convertedToDealId</span></td>            <td>The deal CRM ID, if the lead was converted to a Deal</td>            <td>string</td>            <td>N</td>        </tr>        <tr>            <td><span class='public-api-parameter'>convertedToContactId</span></td>            <td>The contact CRM ID if the lead was converted to a Contact</td>            <td>string</td>            <td>N</td>        </tr>        <tr>            <td><span class='public-api-parameter'>convertedToAccountId</span></td>            <td>The account CRM ID if the lead was converted to an Account</td>            <td>string</td>            <td>N</td>        </tr>    </tbody></table><h3>Example</h3><h4>Request</h4><code>POST https://api.gong.io/v2/crm/object/entities?clientRequestId=1234&integrationId=6286478263646&objectType=LEAD</code><br><br><code>{\"objectId\": \"4v5bt54t553\", \"modifiedDate\": \"2019-01-03T23:45:57+01:00\", \"url\": \"https://crm.com/leads/45k4j5j5k44\", \"emailAddress\": \"jane.doe@acme.com\", \"firstName\": \"Jane\", \"lastName\": \"Doe\", \"title\": \"VP Special Effects\", \"phoneNumber\": \"(912) 507-4395\"}<br>{\"objectId\": \"gf4543gf6th\", \"modifiedDate\": \"2019-01-03T22:45:57Z\", \"emailAddress\": \"john.smith@acme.com\", \"firstName\": \"John\", \"lastName\": \"Smith\", \"isDeleted\": true} // remove lead gf4543gf6th<br>{\"objectId\": \"63473hjg53h\", \"modifiedDate\": \"2019-01-03T23:45:57+01:00\", \"emailAddress\": \"bob.smith@acme.com\", \"firstName\": \"Bob\", \"lastName\": \"Smith\", \"convertedToDealId\": \"dkfj8dfgf87\", \"convertedToContactId\": \"87grhn74hg6\", \"convertedToAccountId\": \"6sjk47jf78d\"} // lead 63473hjg53h converted to account 6sjk47jf78d, contact 87grhn74hg6 and deal dkfj8dfgf87</code><h2>Deal Object</h2><p>A deal in Gong represents a qualified opportunity or contract in a specific account.</p><p>The Deal JSON object includes the following fields:</p><table>    <thead>        <tr>            <th>Name</th>            <th>Description</th>            <th>Data Type</th>            <th>Mandatory</th>        </tr>    </thead>    <tbody>        <tr>            <td><span class='public-api-parameter'>accountId</span></td>            <td>            <p>The ID of the account the deal is associated with in the CRM</p>            <div class='public-api-info'>                <p>An account with the same objectId must be uploaded first in order for the deal to be processed. The accountId needs to match an Account with the same value in its objectId.</p>            </div>            </td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>ownerId</span></td>            <td>            <p>The ID of the owning User in the CRM</p>            <div class='public-api-info'>                <p>This field is a reference to a CRM user which must be mapped to a Gong user via \"/map/users\" API and the Gong user must be set to record or import calls, otherwise the deal will not be processed</p>            </div>            </td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>name</span></td>            <td>The deal’s name</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>createdDate</span></td>            <td>The deal’s creation date and time (ISO-8601 datetime without milliseconds)</td>            <td>datetime</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>estimatedCloseDate</span>*<b>(Deprecated)</b></td>            <td><b>Deprecated</b>. Please use <span class='public-api-parameter'>closeDate</span> instead</td>            <td>date</td>            <td>N</td>        </tr>        <tr>            <td><span class='public-api-parameter'>actualCloseDate</span>*<b>(Deprecated)</b></td>            <td><b>Deprecated</b>. Please use <span class='public-api-parameter'>closeDate</span> instead</td>            <td>date</td>            <td>N</td>        </tr>        <tr>            <td><span class='public-api-parameter'>closeDate</span></td>            <td>The deal’s close date (ISO-8601), without time e.g. \"2021-05-19\"</td>            <td>date</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>isOpen</span></td>            <td>Indicates if the Deal’s status is Open or Closed</td>            <td>boolean</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>isWon</span></td>            <td>Indicates if the Deal’s status is Won or Lost</td>            <td>boolean</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>stage</span></td>            <td>The value of this field must be equal to the internalName of one of the stages uploaded via \"/stages\" API</td>            <td>string</td>            <td>Y</td>        </tr>        <tr>            <td><span class='public-api-parameter'>estimatedAmount</span>**<b>(Deprecated)</b></td>            <td><b>Deprecated</b>. Please use <span class='public-api-parameter'>amount</span> instead</td>            <td>currency</td>            <td>N</td>        </tr>        <tr>            <td><span class='public-api-parameter'>actualAmount</span>**<b>(Deprecated)</b></td>            <td><b>Deprecated</b>. Please use <span class='public-api-parameter'>amount</span> instead</td>            <td>currency</td>            <td>N</td>        </tr>        <tr>            <td><span class='public-api-parameter'>amount</span></td>            <td>The deal’s amount in the currency unit</td>            <td>currency</td>            <td>Y</td>        </tr>    </tbody></table><p>* Either <span class='public-api-parameter'>estimatedCloseDate</span> or <span class='public-api-parameter'>actualCloseDate</span> (or both) must exist in the JSON<br>** Either <span class='public-api-parameter'>estimatedAmount</span> or <span class='public-api-parameter'>actualAmount</span> (or both) must exist in the JSON</p><h3>Example</h3><h4>Request</h4><code>POST https://api.gong.io/v2/crm/object/entities?clientRequestId=1234&integrationId=6286478263646&objectType=DEAL</code><br><br><code>{\"objectId\": \"8608553\", \"modifiedDate\": \"2022-02-04T18:24:59Z\", \"url\": \"http://crm.com/deals/8608553\", \"accountId\": \"5ybyh6n6n65\", \"ownerId\": \"5486951\", \"name\": \"Deal name\", \"createdDate\": \"2022-02-04T17:57:23Z\", \"closeDate\": \"2022-09-04\", \"isOpen\": true, \"isWon\": false, \"stage\": \"discovery\", \"amount\": 7000, \"custom_field_1\": \"2022-02-04T17:57:23.000Z\", \"custom_field_2\": null}</code><h2>Additional Fields</h2><p>In addition to the fields required by Gong, you can also add any other field to each object if the following two conditions are met:<ul>    <li>The field name is defined in the object's schema and has been uploaded using \"/object/schema\" API</li>    <li>The field value matches the type defined in the schema</li></ul></p>

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CRMApi.new
opts = { 
  data_file: 'data_file_example' # String | 
}

begin
  #Upload CRM objects (/v2/crm/object/entities)
  result = api_instance.upload_crm_data_using_post(opts)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CRMApi->upload_crm_data_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **data_file** | **String**|  | [optional] 

### Return type

[**AsyncProcessingResponse**](AsyncProcessingResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json



# **upload_crm_schema_field_using_post**
> SchemaUpdateResponse upload_crm_schema_field_using_post(bodyintegration_idobject_type)

Upload Object Schema (/v2/crm/object/schema)

<style>.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}</style><p>All CRM object fields in Gong must have a representative schema that describes the field (unique name, type, etc.). <br>Any field uploaded by the \"Upload CRM objects\" API (\"/object/entities\" path) that is not described in the schema will be stored in Gong’s raw data storage. However, it will not be parsed by Gong and it will not be available to the end user.</p><p>For new integrations created via \"/integration/new\" API, Gong creates a default schema for each object type (Contact, Account, Deal, Lead) that contains the mandatory and optional fields specified in this guide. See the <b>Upload CRM objects</b> API section for more information.<br>If there are additional fields for any object type that are needed by the end user, send their schema via this API.</p><p><div class='public-api-info'>The schema update request should be sent when:<ul>    <li>You have created a new integration.</li>    <li>There are changes to the schema of any object type. You can also send a schema update request before any request to the '/object/entities' API.</li></ul></div></p><p><div class='public-api-important'>Each schema update request must contain the full schema from your CRM. Fields that were sent in previous requests and no longer exist in your CRM, should be sent in the schema request with \"isDeleted=true\" (only once).</div></p><p>When accessed using a bearer token, this endpoint requires the scope 'api:crm:schema'.</p><h3>Supported Field Types</h3><table>  <thead>  <tr>    <th>Field Type</th>    <th>Format in JSON</th>    <th>Sample Values</th>  </tr>  </thead>  <tbody>  <tr>    <td><span class='public-api-parameter'>BOOLEAN</span></td>    <td>boolean</td>    <td>true, false</td>  </tr>  <tr>    <td><span class='public-api-parameter'>DATE</span></td>    <td>string (ISO-8601 date without time)</td>    <td>\"2020-05-31\"</td>  </tr>  <tr>    <td><span class='public-api-parameter'>DATETIME</span></td>    <td>string (ISO-8601 datetime without milliseconds)</td>    <td>\"2020-12-17T07:37:21+02:00\"<br>\"2020-12-17T05:37:21Z\"</td>  </tr>  <tr>    <td><span class='public-api-parameter'>PICKLIST</span></td>    <td>string - one of the values in an orderedValueList</td>    <td>\"Analyst\"</td>  </tr>  <tr>    <td><span class='public-api-parameter'>NUMBER</span></td>    <td>number</td>    <td>45.66, 8453</td>  </tr>  <tr>    <td><span class='public-api-parameter'>PERCENT</span></td>    <td>number (between 0 to 100)</td>    <td>67.3</td>  </tr>  <tr>    <td><span class='public-api-parameter'>CURRENCY</span>*</td>    <td>number</td>    <td>34.68</td>  </tr>  <tr>    <td><span class='public-api-parameter'>PHONENUMBER</span></td>    <td>string</td>    <td>\"+14055766687\"</td>  </tr>  <tr>    <td><span class='public-api-parameter'>EMAILADDRESS</span></td>    <td>string</td>    <td>\"john.doe@anywhere.com\"</td>  </tr>  <tr>    <td><span class='public-api-parameter'>REFERENCE</span></td>    <td>string - the id of another object</td>    <td>\"48b009drax\"</td>  </tr>  <tr>    <td><span class='public-api-parameter'>ID</span></td>    <td>string - the id of the object</td>    <td>\"843hf8484jr84htg\"</td>  </tr>  <tr>    <td><span class='public-api-parameter'>STRING</span></td>    <td>string</td>    <td>\"whatever you want\"</td>  </tr>  <tr>    <td><span class='public-api-parameter'>STRINGARRAY</span>**</td>    <td>array of strings</td>    <td>[\"http://customer.com\"]</td>  </tr>  <tr>    <td><span class='public-api-parameter'>URL</span></td>    <td>string</td>    <td>\"https://crm.com/account/6d4r578f\"</td>  </tr>  </tbody></table><p>* In the integration send a number value, and specify the correct currency symbol in the Gong UI. Currently  Gong does not support multiple currencies per company.<br>** Can only be used for Gong-defined fields.</p><h3>Example</h3><h4>Request</h4><code>POST https://api.gong.io/v2/crm/object/schema?integrationId=6286478263646&objectType=ACCOUNT</code><br><br><code>[{\"uniqueName\": \"orderId\", \"label\": \"ID\", \"type\": \"ID\", \"lastModified\": \"2020-11-11T08:11:34+01:00\"},<br>{\"uniqueName\": \"parentAccount\", \"label\": \"Main Account\", \"type\": \"REFERENCE\", \"referenceTo\": \"ACCOUNT\", \"lastModified\": \"2020-11-11T08:11:34+01:00\"},<br>{\"uniqueName\": \"category\", \"label\": \"Category\", \"type\": \"PICKLIST\", \"orderedValueList\": [\"Analyst\", \"Competitor\", \"Customer\", \"Integrator\", \"Investor\", \"Partner\", \"Other\"], \"lastModified\": \"2020-11-11T08:11:34+01:00\"}, // custom field<br>{\"uniqueName\": \"industry\", \"isDeleted\": true, \"lastModified\": \"2020-11-21T08:11:34+01:00\"}] // remove custom field</code>

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CRMApi.new
body = [GongAPI::GenericSchemaFieldRequest.new] # Array<GenericSchemaFieldRequest> | fields
integration_id = 789 # Integer | Integration ID generated when creating the integration
object_type = 'object_type_example' # String | Type of object to set the schema for (case-sensitive)


begin
  #Upload Object Schema (/v2/crm/object/schema)
  result = api_instance.upload_crm_schema_field_using_post(bodyintegration_idobject_type)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CRMApi->upload_crm_schema_field_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**Array&lt;GenericSchemaFieldRequest&gt;**](GenericSchemaFieldRequest.md)| fields | 
 **integration_id** | **Integer**| Integration ID generated when creating the integration | 
 **object_type** | **String**| Type of object to set the schema for (case-sensitive) | 

### Return type

[**SchemaUpdateResponse**](SchemaUpdateResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **upload_stages_using_post**
> SchemaUpdateResponse upload_stages_using_post(bodyintegration_id)

Upload Stages (Deprecated)

<style>.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}</style><p>This API is <b>Deprecated</b>. Please use \"/object/entities?objectType=STAGE\" API instead.</p><p>Update the list of stages from the CRM system.</p><p>This API must be called before you upload Deal objects. When you upload your Deal object, make sure that the stage field matches one of the stages you’ve uploaded using this API.</p><div class='public-api-info'><p>The upload stages request should only be sent after:</p><ul>    <li>You have created a new integration.</li>    <li>There are any changes to the list of stages in the CRM. You can also send a stages update request before any request to the '/object/entities' API.</li></ul></div><p>When accessed using a bearer token, this endpoint requires the scope 'api:crm:schema'.</p>

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CRMApi.new
body = [GongAPI::GenericDealStageRequest.new] # Array<GenericDealStageRequest> | stages
integration_id = 789 # Integer | Integration ID generated when creating the integration


begin
  #Upload Stages (Deprecated)
  result = api_instance.upload_stages_using_post(bodyintegration_id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CRMApi->upload_stages_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**Array&lt;GenericDealStageRequest&gt;**](GenericDealStageRequest.md)| stages | 
 **integration_id** | **Integer**| Integration ID generated when creating the integration | 

### Return type

[**SchemaUpdateResponse**](SchemaUpdateResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



