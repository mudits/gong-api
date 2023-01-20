# GongAPI::EngagementInBetaPhaseApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**content_shared_using_put**](EngagementInBetaPhaseApi.md#content_shared_using_put) | **PUT** /v2/customer-engagement/content/shared | Report event of a content share (/v2/customer-engagement/content/shared)
[**content_viewed_using_put**](EngagementInBetaPhaseApi.md#content_viewed_using_put) | **PUT** /v2/customer-engagement/content/viewed | Report event of a content view (/v2/customer-engagement/content/viewed)
[**custom_action_using_put**](EngagementInBetaPhaseApi.md#custom_action_using_put) | **PUT** /v2/customer-engagement/action | Report event of a custom action (/v2/customer-engagement/action)

# **content_shared_using_put**
> BaseResponse content_shared_using_put(body)

Report event of a content share (/v2/customer-engagement/content/shared)

Push engagement events into Gong and display them as events in Gong’s activity timeline, when a Gong user shares content with external participants (for example, a contract was “shared” by the account executive with his prospects)  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:engagement-data:write'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::EngagementInBetaPhaseApi.new
body = GongAPI::ContentSharedEvent.new # ContentSharedEvent | request


begin
  #Report event of a content share (/v2/customer-engagement/content/shared)
  result = api_instance.content_shared_using_put(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling EngagementInBetaPhaseApi->content_shared_using_put: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ContentSharedEvent**](ContentSharedEvent.md)| request | 

### Return type

[**BaseResponse**](BaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*



# **content_viewed_using_put**
> BaseResponse content_viewed_using_put(body)

Report event of a content view (/v2/customer-engagement/content/viewed)

Push engagement events into Gong and display them as events in Gong’s activity timeline, when a content is viewed by an external participant (for example, a contract was “viewed” by the prospect)  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:engagement-data:write'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::EngagementInBetaPhaseApi.new
body = GongAPI::ContentViewedEvent.new # ContentViewedEvent | request


begin
  #Report event of a content view (/v2/customer-engagement/content/viewed)
  result = api_instance.content_viewed_using_put(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling EngagementInBetaPhaseApi->content_viewed_using_put: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ContentViewedEvent**](ContentViewedEvent.md)| request | 

### Return type

[**BaseResponse**](BaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*



# **custom_action_using_put**
> BaseResponse custom_action_using_put(body)

Report event of a custom action (/v2/customer-engagement/action)

Push engagement events into Gong and display them as events in Gong’s activity timeline, when a content is engaged by an external participant (for example, a contract was “signed” by the prospect)  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:engagement-data:write'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::EngagementInBetaPhaseApi.new
body = GongAPI::CustomActionEvent.new # CustomActionEvent | request


begin
  #Report event of a custom action (/v2/customer-engagement/action)
  result = api_instance.custom_action_using_put(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling EngagementInBetaPhaseApi->custom_action_using_put: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**CustomActionEvent**](CustomActionEvent.md)| request | 

### Return type

[**BaseResponse**](BaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*



