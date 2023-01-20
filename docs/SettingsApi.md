# GongAPI::SettingsApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**list_scorecards_using_get**](SettingsApi.md#list_scorecards_using_get) | **GET** /v2/settings/scorecards | Retrieve scorecards details (/v2/settings/scorecards)
[**list_workspaces_using_get**](SettingsApi.md#list_workspaces_using_get) | **GET** /v2/workspaces | List all company workspaces (/v2/workspaces)

# **list_scorecards_using_get**
> Scorecards list_scorecards_using_get

Retrieve scorecards details (/v2/settings/scorecards)

Retrieve all the scorecards within the Gong system.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:settings:scorecards:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::SettingsApi.new

begin
  #Retrieve scorecards details (/v2/settings/scorecards)
  result = api_instance.list_scorecards_using_get
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling SettingsApi->list_scorecards_using_get: #{e}"
end
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**Scorecards**](Scorecards.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **list_workspaces_using_get**
> WorkspacesMetadata list_workspaces_using_get

List all company workspaces (/v2/workspaces)

Returns a list of all workspaces including their details.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:workspaces:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::SettingsApi.new

begin
  #List all company workspaces (/v2/workspaces)
  result = api_instance.list_workspaces_using_get
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling SettingsApi->list_workspaces_using_get: #{e}"
end
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**WorkspacesMetadata**](WorkspacesMetadata.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



