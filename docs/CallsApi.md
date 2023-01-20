# GongAPI::CallsApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_call_recording_using_put**](CallsApi.md#add_call_recording_using_put) | **PUT** /v2/calls/{id}/media | Add call media (/v2/calls/{id}/media)
[**add_call_using_post**](CallsApi.md#add_call_using_post) | **POST** /v2/calls | Add new call (/v2/calls)
[**get_call_transcripts_using_post**](CallsApi.md#get_call_transcripts_using_post) | **POST** /v2/calls/transcript | Retrieve transcripts of calls by date or callIds (/v2/calls/transcript)
[**get_call_using_get**](CallsApi.md#get_call_using_get) | **GET** /v2/calls/{id} | Retrieve data for a specific call (/v2/calls/{id})
[**list_calls_extensive_using_post**](CallsApi.md#list_calls_extensive_using_post) | **POST** /v2/calls/extensive | Retrieve detailed call data by various filters (/v2/calls/extensive)
[**list_calls_using_get1**](CallsApi.md#list_calls_using_get1) | **GET** /v2/calls | Retrieve call data by date range (/v2/calls)
[**list_crm_calls_manual_association_using_get**](CallsApi.md#list_crm_calls_manual_association_using_get) | **GET** /v2/calls/manual-crm-associations | List all calls that were manually associated with CRM objects (/v2/calls/manual-crm-associations) in Beta Phase

# **add_call_recording_using_put**
> NewCallRecordingResponse add_call_recording_using_put(id, opts)

Add call media (/v2/calls/{id}/media)

Adds a call media, recorded by a telephony system (PBX) or other media recording facility. Gong accepts call recordings in various audio and video file formats, including WAV, MP3, MP4, MKV and FLAC. If uploading a dual-channel (stereo) file separated by speaker, make sure to specify which channel correspondsto the company team member (rep) in the parties/mediaChannelId parameter of the Add New Call operation.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:calls:create'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CallsApi.new
id = 'id_example' # String | callId returned from 'Add New Call' request
opts = { 
  media_file: 'media_file_example' # String | 
}

begin
  #Add call media (/v2/calls/{id}/media)
  result = api_instance.add_call_recording_using_put(id, opts)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CallsApi->add_call_recording_using_put: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **String**| callId returned from &#x27;Add New Call&#x27; request | 
 **media_file** | **String**|  | [optional] 

### Return type

[**NewCallRecordingResponse**](NewCallRecordingResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json



# **add_call_using_post**
> NewCallAddingResponse add_call_using_post(body)

Add new call (/v2/calls)

When using this endpoint, either provide a downloadMediaUrl or use the returned callId in a follow-up request to /v2/calls/{id}/media to upload the media file.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:calls:create'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CallsApi.new
body = GongAPI::NewCallAddingRequest.new # NewCallAddingRequest | newCallAddingRequest


begin
  #Add new call (/v2/calls)
  result = api_instance.add_call_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CallsApi->add_call_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**NewCallAddingRequest**](NewCallAddingRequest.md)| newCallAddingRequest | 

### Return type

[**NewCallAddingResponse**](NewCallAddingResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **get_call_transcripts_using_post**
> CallTranscripts get_call_transcripts_using_post(body)

Retrieve transcripts of calls by date or callIds (/v2/calls/transcript)

Lists the transcripts of calls that took place during a specified date range and have specified callIds.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:calls:read:transcript'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CallsApi.new
body = GongAPI::RequestCallsFilter.new # RequestCallsFilter | callsRequest


begin
  #Retrieve transcripts of calls by date or callIds (/v2/calls/transcript)
  result = api_instance.get_call_transcripts_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CallsApi->get_call_transcripts_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**RequestCallsFilter**](RequestCallsFilter.md)| callsRequest | 

### Return type

[**CallTranscripts**](CallTranscripts.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **get_call_using_get**
> SpecificCall get_call_using_get(id)

Retrieve data for a specific call (/v2/calls/{id})

Retrieve data for a specific call.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:calls:read:basic'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CallsApi.new
id = 'id_example' # String | Gong's unique numeric identifier for the call (up to 20 digits).


begin
  #Retrieve data for a specific call (/v2/calls/{id})
  result = api_instance.get_call_using_get(id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CallsApi->get_call_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **String**| Gong&#x27;s unique numeric identifier for the call (up to 20 digits). | 

### Return type

[**SpecificCall**](SpecificCall.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **list_calls_extensive_using_post**
> Calls list_calls_extensive_using_post(body)

Retrieve detailed call data by various filters (/v2/calls/extensive)

Lists detailed call data for calls that took place during a specified date range, have specified call IDs or hosted by specified users.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:calls:read:extensive'.  Moreover, clients requesting media download URLs by the contentSelector.exposedFields.media field should also have the scope 'api:calls:read:media-url'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CallsApi.new
body = GongAPI::RequestCallsRequestFilterWithOwnersContentSelector.new # RequestCallsRequestFilterWithOwnersContentSelector | callsRequest


begin
  #Retrieve detailed call data by various filters (/v2/calls/extensive)
  result = api_instance.list_calls_extensive_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CallsApi->list_calls_extensive_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**RequestCallsRequestFilterWithOwnersContentSelector**](RequestCallsRequestFilterWithOwnersContentSelector.md)| callsRequest | 

### Return type

[**Calls**](Calls.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **list_calls_using_get1**
> CallsResponse list_calls_using_get1(from_date_time, to_date_time, opts)

Retrieve call data by date range (/v2/calls)

List calls that took place during a specified date range.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:calls:read:basic'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CallsApi.new
from_date_time = 'from_date_time_example' # String | The date from which to list calls, in the ISO-8601 format (e.g., '2018-02-18T02:30:00-07:00' or '2018-02-18T08:00:00Z', where Z stands for UTC); if not specified, the calls start with the earliest recorded call. For web-conference calls recorded by Gong, the date denotes its scheduled time, otherwise, it denotes its actual start time.
to_date_time = 'to_date_time_example' # String | The date until which to list calls, in the ISO-8601 format (e.g., '2018-02-18T02:30:00-07:00' or '2018-02-18T08:00:00Z', where Z stands for UTC); if not specified, the calls end with the latest recorded call. For web-conference calls recorded by Gong, the date denotes its scheduled time, otherwise, it denotes its actual start time.
opts = { 
  cursor: 'cursor_example', # String | When paging is needed, provide the value supplied by the previous API call to bring the following page of records.
  workspace_id: 'workspace_id_example' # String | Optional Workspace identifier, if supplied the API will return only the calls belonging to this workspace.
}

begin
  #Retrieve call data by date range (/v2/calls)
  result = api_instance.list_calls_using_get1(from_date_time, to_date_time, opts)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CallsApi->list_calls_using_get1: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **from_date_time** | **String**| The date from which to list calls, in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC); if not specified, the calls start with the earliest recorded call. For web-conference calls recorded by Gong, the date denotes its scheduled time, otherwise, it denotes its actual start time. | 
 **to_date_time** | **String**| The date until which to list calls, in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC); if not specified, the calls end with the latest recorded call. For web-conference calls recorded by Gong, the date denotes its scheduled time, otherwise, it denotes its actual start time. | 
 **cursor** | **String**| When paging is needed, provide the value supplied by the previous API call to bring the following page of records. | [optional] 
 **workspace_id** | **String**| Optional Workspace identifier, if supplied the API will return only the calls belonging to this workspace. | [optional] 

### Return type

[**CallsResponse**](CallsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **list_crm_calls_manual_association_using_get**
> ManualAssociationResponse list_crm_calls_manual_association_using_get(opts)

List all calls that were manually associated with CRM objects (/v2/calls/manual-crm-associations) in Beta Phase

Returns a list of all calls that were manually associated or re-associated with CRM account and deal/opportunity since a given time.  Actions will be listed in the ascending order of their timing.   Notice if a call was associated and later re-associated the API will return both events.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:crm-calls:manual-association:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::CallsApi.new
opts = { 
  cursor: 'cursor_example', # String | When paging is needed, provide the value supplied by the previous API call to bring the following page of records.
  from_date_time: 'from_date_time_example' # String | Association time filter - only the associations made after that time will be listed. The time is in the ISO-8601 format (e.g., '2018-02-18T02:30:00-07:00' or '2018-02-18T08:00:00Z', where Z stands for UTC); if not specified all association events will be listed.
}

begin
  #List all calls that were manually associated with CRM objects (/v2/calls/manual-crm-associations) in Beta Phase
  result = api_instance.list_crm_calls_manual_association_using_get(opts)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling CallsApi->list_crm_calls_manual_association_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **cursor** | **String**| When paging is needed, provide the value supplied by the previous API call to bring the following page of records. | [optional] 
 **from_date_time** | **String**| Association time filter - only the associations made after that time will be listed. The time is in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC); if not specified all association events will be listed. | [optional] 

### Return type

[**ManualAssociationResponse**](ManualAssociationResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



