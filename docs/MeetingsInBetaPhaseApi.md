# GongAPI::MeetingsInBetaPhaseApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_meeting_using_post**](MeetingsInBetaPhaseApi.md#add_meeting_using_post) | **POST** /v2/meetings | Create a New Gong Meeting (/v2/meetings)
[**delete_meeting_using_delete**](MeetingsInBetaPhaseApi.md#delete_meeting_using_delete) | **DELETE** /v2/meetings/{meetingId} | Delete a Gong Meeting (/v2/meetings)
[**integration_status_using_post**](MeetingsInBetaPhaseApi.md#integration_status_using_post) | **POST** /v2/meetings/integration/status | Validate Gong meeting Integration (/v2/meetings/integration/status)
[**update_meeting_using_put**](MeetingsInBetaPhaseApi.md#update_meeting_using_put) | **PUT** /v2/meetings/{meetingId} | Update a Gong Meeting (/v2/meetings/{meetingId})

# **add_meeting_using_post**
> NewMeetingResponse add_meeting_using_post(body)

Create a New Gong Meeting (/v2/meetings)

When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:meetings:user:create'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::MeetingsInBetaPhaseApi.new
body = GongAPI::NewMeetingRequest.new # NewMeetingRequest | newMeetingRequest


begin
  #Create a New Gong Meeting (/v2/meetings)
  result = api_instance.add_meeting_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling MeetingsInBetaPhaseApi->add_meeting_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**NewMeetingRequest**](NewMeetingRequest.md)| newMeetingRequest | 

### Return type

[**NewMeetingResponse**](NewMeetingResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **delete_meeting_using_delete**
> DeleteMeetingRequest delete_meeting_using_delete(bodymeeting_id)

Delete a Gong Meeting (/v2/meetings)

When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:meetings:user:delete'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::MeetingsInBetaPhaseApi.new
body = GongAPI::DeleteMeetingRequest.new # DeleteMeetingRequest | request
meeting_id = 789 # Integer | Gong's unique identifier for the meeting (up to 20 digits).


begin
  #Delete a Gong Meeting (/v2/meetings)
  result = api_instance.delete_meeting_using_delete(bodymeeting_id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling MeetingsInBetaPhaseApi->delete_meeting_using_delete: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**DeleteMeetingRequest**](DeleteMeetingRequest.md)| request | 
 **meeting_id** | **Integer**| Gong&#x27;s unique identifier for the meeting (up to 20 digits). | 

### Return type

[**DeleteMeetingRequest**](DeleteMeetingRequest.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json



# **integration_status_using_post**
> IntegrationStatusResponse integration_status_using_post(body)

Validate Gong meeting Integration (/v2/meetings/integration/status)

When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:meetings:integration:status'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::MeetingsInBetaPhaseApi.new
body = GongAPI::IntegrationStatusRequest.new # IntegrationStatusRequest | integrationStatusRequest


begin
  #Validate Gong meeting Integration (/v2/meetings/integration/status)
  result = api_instance.integration_status_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling MeetingsInBetaPhaseApi->integration_status_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IntegrationStatusRequest**](IntegrationStatusRequest.md)| integrationStatusRequest | 

### Return type

[**IntegrationStatusResponse**](IntegrationStatusResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **update_meeting_using_put**
> UpdateMeetingResponse update_meeting_using_put(bodymeeting_id)

Update a Gong Meeting (/v2/meetings/{meetingId})

When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:meetings:user:update'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::MeetingsInBetaPhaseApi.new
body = GongAPI::UpdateMeetingRequest.new # UpdateMeetingRequest | updateMeetingRequest
meeting_id = 789 # Integer | Gong's unique identifier for the meeting (up to 20 digits).


begin
  #Update a Gong Meeting (/v2/meetings/{meetingId})
  result = api_instance.update_meeting_using_put(bodymeeting_id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling MeetingsInBetaPhaseApi->update_meeting_using_put: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**UpdateMeetingRequest**](UpdateMeetingRequest.md)| updateMeetingRequest | 
 **meeting_id** | **Integer**| Gong&#x27;s unique identifier for the meeting (up to 20 digits). | 

### Return type

[**UpdateMeetingResponse**](UpdateMeetingResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



