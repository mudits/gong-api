# GongAPI::PermissionsApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_users_access_to_calls_using_put**](PermissionsApi.md#add_users_access_to_calls_using_put) | **PUT** /v2/calls/users-access | Give individual users access to calls (/v2/calls/users-access)
[**create_permission_profile_using_post**](PermissionsApi.md#create_permission_profile_using_post) | **POST** /v2/permission-profile | Create permission profile (/v2/permission-profile)
[**delete_users_access_to_calls_using_delete**](PermissionsApi.md#delete_users_access_to_calls_using_delete) | **DELETE** /v2/calls/users-access | Remove specific individual users access from calls (/v2/calls/users-access)
[**get_permission_profile_using_get**](PermissionsApi.md#get_permission_profile_using_get) | **GET** /v2/permission-profile | Permission profile for a given profile Id (/v2/permission-profile)
[**get_users_access_to_calls_using_get**](PermissionsApi.md#get_users_access_to_calls_using_get) | **GET** /v2/calls/users-access | Retrieve users that have specific individual access to calls (/v2/calls/users-access)
[**list_permission_profile_users_using_get**](PermissionsApi.md#list_permission_profile_users_using_get) | **GET** /v2/permission-profile/users | List all users attached to a given permission profile (/v2/permission-profile/users)
[**list_permission_profile_using_get**](PermissionsApi.md#list_permission_profile_using_get) | **GET** /v2/all-permission-profiles | List all company permission profiles for a given workspace (/v2/all-permission-profiles)
[**update_permission_profile_using_put**](PermissionsApi.md#update_permission_profile_using_put) | **PUT** /v2/permission-profile | Update permission profile (/v2/permission-profile)

# **add_users_access_to_calls_using_put**
> BaseResponse add_users_access_to_calls_using_put(body)

Give individual users access to calls (/v2/calls/users-access)

Give individual users access to calls.  If a user already has access (perhaps the call was shared with them, or they have access through their permission profiles) the request will have no effect.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:call-user-access:write'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::PermissionsApi.new
body = GongAPI::CallsUsersAccessAddDto.new # CallsUsersAccessAddDto | callsUsersAccessAddDto


begin
  #Give individual users access to calls (/v2/calls/users-access)
  result = api_instance.add_users_access_to_calls_using_put(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling PermissionsApi->add_users_access_to_calls_using_put: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**CallsUsersAccessAddDto**](CallsUsersAccessAddDto.md)| callsUsersAccessAddDto | 

### Return type

[**BaseResponse**](BaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **create_permission_profile_using_post**
> PermissionProfileResponse create_permission_profile_using_post(bodyworkspace_id)

Create permission profile (/v2/permission-profile)

Create a permission profile in a given workspace.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::PermissionsApi.new
body = GongAPI::PermissionProfileDTO.new # PermissionProfileDTO | permissionProfileDTO
workspace_id = 'workspace_id_example' # String | Workspace identifier.  You can retrieve the workspace using the \"workspaces\" (under \"Settings\") API.


begin
  #Create permission profile (/v2/permission-profile)
  result = api_instance.create_permission_profile_using_post(bodyworkspace_id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling PermissionsApi->create_permission_profile_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**PermissionProfileDTO**](PermissionProfileDTO.md)| permissionProfileDTO | 
 **workspace_id** | **String**| Workspace identifier.  You can retrieve the workspace using the \&quot;workspaces\&quot; (under \&quot;Settings\&quot;) API. | 

### Return type

[**PermissionProfileResponse**](PermissionProfileResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **delete_users_access_to_calls_using_delete**
> BaseResponse delete_users_access_to_calls_using_delete(body)

Remove specific individual users access from calls (/v2/calls/users-access)

Remove individual user access from calls. The request can only remove access previously given by the /v2/calls/users-access API.  If a given user does not have access to the call, they will be unaffected.  If a given user does have access to the call, but not through the pubic API (for example if the call was shared with the user), the user's access will remain unchanged.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:call-user-access:write'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::PermissionsApi.new
body = GongAPI::CallsUsersAccessDeleteDto.new # CallsUsersAccessDeleteDto | callsUsersAccessDeleteDto


begin
  #Remove specific individual users access from calls (/v2/calls/users-access)
  result = api_instance.delete_users_access_to_calls_using_delete(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling PermissionsApi->delete_users_access_to_calls_using_delete: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**CallsUsersAccessDeleteDto**](CallsUsersAccessDeleteDto.md)| callsUsersAccessDeleteDto | 

### Return type

[**BaseResponse**](BaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json



# **get_permission_profile_using_get**
> PermissionProfileResponse get_permission_profile_using_get(profile_id)

Permission profile for a given profile Id (/v2/permission-profile)

Returns a permission profile.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::PermissionsApi.new
profile_id = 'profile_id_example' # String | Permission profile identifier.


begin
  #Permission profile for a given profile Id (/v2/permission-profile)
  result = api_instance.get_permission_profile_using_get(profile_id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling PermissionsApi->get_permission_profile_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **profile_id** | **String**| Permission profile identifier. | 

### Return type

[**PermissionProfileResponse**](PermissionProfileResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_users_access_to_calls_using_get**
> CallsAccessDetailsResponse get_users_access_to_calls_using_get(body)

Retrieve users that have specific individual access to calls (/v2/calls/users-access)

Returns a list of users who have received individual access to calls through the API.  This endpoint doesn't cover user that have access for other reasons (such as sharing recipients, or access through permission profiles).  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:call-user-access:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::PermissionsApi.new
body = GongAPI::RequestCallsAccessGetDto.new # RequestCallsAccessGetDto | callsAccessGetDto


begin
  #Retrieve users that have specific individual access to calls (/v2/calls/users-access)
  result = api_instance.get_users_access_to_calls_using_get(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling PermissionsApi->get_users_access_to_calls_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**RequestCallsAccessGetDto**](RequestCallsAccessGetDto.md)| callsAccessGetDto | 

### Return type

[**CallsAccessDetailsResponse**](CallsAccessDetailsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json



# **list_permission_profile_users_using_get**
> PermissionProfileUsersResponse list_permission_profile_users_using_get(profile_id)

List all users attached to a given permission profile (/v2/permission-profile/users)

Returns a list of all users whose access is controlled by the given permission profile.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:users:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::PermissionsApi.new
profile_id = 'profile_id_example' # String | Permission profile identifier.


begin
  #List all users attached to a given permission profile (/v2/permission-profile/users)
  result = api_instance.list_permission_profile_users_using_get(profile_id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling PermissionsApi->list_permission_profile_users_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **profile_id** | **String**| Permission profile identifier. | 

### Return type

[**PermissionProfileUsersResponse**](PermissionProfileUsersResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **list_permission_profile_using_get**
> PermissionProfilesResponse list_permission_profile_using_get(workspace_id)

List all company permission profiles for a given workspace (/v2/all-permission-profiles)

Returns a list of all permission profiles.  The listing is in the alphabetical order of the profile names.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::PermissionsApi.new
workspace_id = 'workspace_id_example' # String | Workspace identifier, the API will return only the profiles belonging to this workspace.  You can retrieve the workspace using the \"workspaces\" (under \"Settings\") API.


begin
  #List all company permission profiles for a given workspace (/v2/all-permission-profiles)
  result = api_instance.list_permission_profile_using_get(workspace_id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling PermissionsApi->list_permission_profile_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspace_id** | **String**| Workspace identifier, the API will return only the profiles belonging to this workspace.  You can retrieve the workspace using the \&quot;workspaces\&quot; (under \&quot;Settings\&quot;) API. | 

### Return type

[**PermissionProfilesResponse**](PermissionProfilesResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **update_permission_profile_using_put**
> PermissionProfileResponse update_permission_profile_using_put(bodyprofile_id)

Update permission profile (/v2/permission-profile)

Update a permission profile.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::PermissionsApi.new
body = GongAPI::PermissionProfileDTO.new # PermissionProfileDTO | permissionProfileDTO
profile_id = 'profile_id_example' # String | Permission profile identifier.


begin
  #Update permission profile (/v2/permission-profile)
  result = api_instance.update_permission_profile_using_put(bodyprofile_id)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling PermissionsApi->update_permission_profile_using_put: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**PermissionProfileDTO**](PermissionProfileDTO.md)| permissionProfileDTO | 
 **profile_id** | **String**| Permission profile identifier. | 

### Return type

[**PermissionProfileResponse**](PermissionProfileResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



