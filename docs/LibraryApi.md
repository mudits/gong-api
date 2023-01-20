# GongAPI::LibraryApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_calls_in_specific_folder_using_get**](LibraryApi.md#get_calls_in_specific_folder_using_get) | **GET** /v2/library/folder-content | List of calls in a specific folder (/v2/library/folder-content)
[**get_library_structure_using_get**](LibraryApi.md#get_library_structure_using_get) | **GET** /v2/library/folders | Retrieve Library folders (/v2/library/folders)

# **get_calls_in_specific_folder_using_get**
> LibraryFolderListOfCallsResponse get_calls_in_specific_folder_using_get(opts)

List of calls in a specific folder (/v2/library/folder-content)

Given a folder id, this endpoint retrieves a list of calls in it.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:library:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::LibraryApi.new
opts = { 
  folder_id: 'folder_id_example' # String | Gong's unique numeric identifier for the folder (up to 20 digits).
}

begin
  #List of calls in a specific folder (/v2/library/folder-content)
  result = api_instance.get_calls_in_specific_folder_using_get(opts)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling LibraryApi->get_calls_in_specific_folder_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **folder_id** | **String**| Gong&#x27;s unique numeric identifier for the folder (up to 20 digits). | [optional] 

### Return type

[**LibraryFolderListOfCallsResponse**](LibraryFolderListOfCallsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_library_structure_using_get**
> LibraryResponse get_library_structure_using_get(opts)

Retrieve Library folders (/v2/library/folders)

Use this endpoint to retrieve a list of public library folders. We do not allow retrieval of either private or archived folders.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:library:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::LibraryApi.new
opts = { 
  workspace_id: 'workspace_id_example' # String | Workspace identifier. We will retrieve folders which are related to this specific workspace.
}

begin
  #Retrieve Library folders (/v2/library/folders)
  result = api_instance.get_library_structure_using_get(opts)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling LibraryApi->get_library_structure_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspace_id** | **String**| Workspace identifier. We will retrieve folders which are related to this specific workspace. | [optional] 

### Return type

[**LibraryResponse**](LibraryResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



