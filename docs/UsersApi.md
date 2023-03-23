# GongAPI::UsersApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_user_history_using_get**](UsersApi.md#get_user_history_using_get) | **GET** /v2/users/{id}/settings-history | Retrieve user history (/v2/users/{id}/settings-history)
[**get_user_using_get**](UsersApi.md#get_user_using_get) | **GET** /v2/users/{id} | Retrieve user (/v2/users/{id})
[**list_multiple_users_using_post**](UsersApi.md#list_multiple_users_using_post) | **POST** /v2/users/extensive | List users by filter (/v2/users/extensive)
[**list_users_using_get**](UsersApi.md#list_users_using_get) | **GET** /v2/users | List all users (/v2/users)

# **get_user_history_using_get**
> SettingsHistory get_user_history_using_get(id)

Retrieve user history (/v2/users/{id}/settings-history)

Retrieve a specific user's history.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:users:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::UsersApi.new
id = 'id_example' # String | Gong's unique numeric identifier for the user (up to 20 digits).


begin
  #Retrieve user history (/v2/users/{id}/settings-history)
  result = api_instance.get_user_history_using_get(id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling UsersApi->get_user_history_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **String**| Gong&#x27;s unique numeric identifier for the user (up to 20 digits). | 

### Return type

[**SettingsHistory**](SettingsHistory.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_user_using_get**
> User get_user_using_get(id)

Retrieve user (/v2/users/{id})

Retrieve a specific user.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:users:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::UsersApi.new
id = 'id_example' # String | Gong's unique numeric identifier for the user (up to 20 digits).


begin
  #Retrieve user (/v2/users/{id})
  result = api_instance.get_user_using_get(id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling UsersApi->get_user_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **String**| Gong&#x27;s unique numeric identifier for the user (up to 20 digits). | 

### Return type

[**User**](User.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **list_multiple_users_using_post**
> UsersMetadata list_multiple_users_using_post(body)

List users by filter (/v2/users/extensive)

List multiple Users.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:users:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::UsersApi.new
body = GongAPI::RequestMultipleUsersRequestWithCreationDates.new # RequestMultipleUsersRequestWithCreationDates | multipleUsersRequest


begin
  #List users by filter (/v2/users/extensive)
  result = api_instance.list_multiple_users_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling UsersApi->list_multiple_users_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**RequestMultipleUsersRequestWithCreationDates**](RequestMultipleUsersRequestWithCreationDates.md)| multipleUsersRequest | 

### Return type

[**UsersMetadata**](UsersMetadata.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **list_users_using_get**
> UsersMetadata list_users_using_get(opts)

List all users (/v2/users)

List all of the company's users.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:users:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::UsersApi.new
opts = { 
  cursor: 'cursor_example', # String | When paging is needed, provide the value supplied by the previous API call to bring the following page of records.
  include_avatars: true # BOOLEAN | Avatars are synthetic users representing Gong employees (CSMs and support providers) when they access your instance. References to avatars' IDs may be found in the outputs of other API endpoints. This parameter is optional, if not provided avatars will not be included in the results.
}

begin
  #List all users (/v2/users)
  result = api_instance.list_users_using_get(opts)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling UsersApi->list_users_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **cursor** | **String**| When paging is needed, provide the value supplied by the previous API call to bring the following page of records. | [optional] 
 **include_avatars** | **BOOLEAN**| Avatars are synthetic users representing Gong employees (CSMs and support providers) when they access your instance. References to avatars&#x27; IDs may be found in the outputs of other API endpoints. This parameter is optional, if not provided avatars will not be included in the results. | [optional] 

### Return type

[**UsersMetadata**](UsersMetadata.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



