# GongAPI::AuditingApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**list_logs_using_get**](AuditingApi.md#list_logs_using_get) | **GET** /v2/logs | Retrieve logs data by type and time range (/v2/logs)

# **list_logs_using_get**
> LogsResponse list_logs_using_get(from_date_time, log_type, opts)

Retrieve logs data by type and time range (/v2/logs)

List log entries that took place during a specified time range.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:logs:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::AuditingApi.new
from_date_time = 'from_date_time_example' # String | The time from which to retrieve log records, in the ISO-8601 format (e.g., '2018-02-18T02:30:00-07:00' or '2018-02-18T08:00:00Z', where Z stands for UTC).
log_type = 'log_type_example' # String | Type of logs requested.
opts = { 
  cursor: 'cursor_example', # String | When paging is needed, provide the value supplied by the previous API call to bring the following page of records.
  to_date_time: 'to_date_time_example' # String | The time until which to retrieve log records, in the ISO-8601 format (e.g., '2018-02-18T02:30:00-07:00' or '2018-02-18T08:00:00Z', where Z stands for UTC); if not specified, the logs end with the latest recorded log.
}

begin
  #Retrieve logs data by type and time range (/v2/logs)
  result = api_instance.list_logs_using_get(from_date_time, log_type, opts)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling AuditingApi->list_logs_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **from_date_time** | **String**| The time from which to retrieve log records, in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | 
 **log_type** | **String**| Type of logs requested. | 
 **cursor** | **String**| When paging is needed, provide the value supplied by the previous API call to bring the following page of records. | [optional] 
 **to_date_time** | **String**| The time until which to retrieve log records, in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC); if not specified, the logs end with the latest recorded log. | [optional] 

### Return type

[**LogsResponse**](LogsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



