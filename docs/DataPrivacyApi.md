# GongAPI::DataPrivacyApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**find_all_references_to_email_address_using_get**](DataPrivacyApi.md#find_all_references_to_email_address_using_get) | **GET** /v2/data-privacy/data-for-email-address | Retrieve all references to an email address. (/v2/data-privacy/data-for-email-address)
[**find_all_references_to_phone_number_using_get**](DataPrivacyApi.md#find_all_references_to_phone_number_using_get) | **GET** /v2/data-privacy/data-for-phone-number | Retrieve all references to a phone number. (/v2/data-privacy/data-for-phone-number)
[**purge_email_address_using_post**](DataPrivacyApi.md#purge_email_address_using_post) | **POST** /v2/data-privacy/erase-data-for-email-address | Delete the email address, and all associated elements (/v2/data-privacy/erase-data-for-email-address)
[**purge_phone_number_using_post**](DataPrivacyApi.md#purge_phone_number_using_post) | **POST** /v2/data-privacy/erase-data-for-phone-number | Delete the phone number, and all associated elements (/v2/data-privacy/erase-data-for-phone-number)

# **find_all_references_to_email_address_using_get**
> EmailAddressReferences find_all_references_to_email_address_using_get(email_address)

Retrieve all references to an email address. (/v2/data-privacy/data-for-email-address)

Shows the elements in the Gong system that reference the given email address. Given an emails address, this endpoint returns details of all calls and email messages that reference this address, and any leads or contacts with this email address.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:data-privacy:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::DataPrivacyApi.new
email_address = 'email_address_example' # String | The email address.


begin
  #Retrieve all references to an email address. (/v2/data-privacy/data-for-email-address)
  result = api_instance.find_all_references_to_email_address_using_get(email_address)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling DataPrivacyApi->find_all_references_to_email_address_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **email_address** | **String**| The email address. | 

### Return type

[**EmailAddressReferences**](EmailAddressReferences.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **find_all_references_to_phone_number_using_get**
> PhoneNumberReferences find_all_references_to_phone_number_using_get(phone_number)

Retrieve all references to a phone number. (/v2/data-privacy/data-for-phone-number)

Shows the elements in the Gong system that reference the given phone number. Given a phone number, this endpoint returns details of any leads or contacts with this phone number and their associated calls and email messages.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:data-privacy:read'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::DataPrivacyApi.new
phone_number = 'phone_number_example' # String | The phone number.  This number must start with a + (plus) sign followed by the country code, area code, and local phone number. All other non-digits are ignored.  The following are examples of permitted phone numbers: +1 425 555 2671, +1-425-555-2671, +1 425 5552671, +14255552671, +1 425 555 26 71, +1(425) 555-2671, etc.  Note: This parameter should be URL-encoded.


begin
  #Retrieve all references to a phone number. (/v2/data-privacy/data-for-phone-number)
  result = api_instance.find_all_references_to_phone_number_using_get(phone_number)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling DataPrivacyApi->find_all_references_to_phone_number_using_get: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **phone_number** | **String**| The phone number.  This number must start with a + (plus) sign followed by the country code, area code, and local phone number. All other non-digits are ignored.  The following are examples of permitted phone numbers: +1 425 555 2671, +1-425-555-2671, +1 425 5552671, +14255552671, +1 425 555 26 71, +1(425) 555-2671, etc.  Note: This parameter should be URL-encoded. | 

### Return type

[**PhoneNumberReferences**](PhoneNumberReferences.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **purge_email_address_using_post**
> BaseResponse purge_email_address_using_post(email_address)

Delete the email address, and all associated elements (/v2/data-privacy/erase-data-for-email-address)

Given an email address, this endpoint deletes from the Gong system any calls or email messages that reference this address. Email messages sent to or from the address are deleted. Calls where the email address appears (as a lead, contact, attendee or speaker) are deleted. Leads or Contacts with the email address are deleted. The deletion is not immediate, and may take several hours to complete.  This endpoint contains a data integrity protection mechanism to prevent the deletion of an abnormal number of objects. If the deletion fails please contact support at help@gong.io  Delete the data from your CRM and email system before performing this operation so that private data is not re-imported into Gong.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:data-privacy:delete'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::DataPrivacyApi.new
email_address = 'email_address_example' # String | The email address.


begin
  #Delete the email address, and all associated elements (/v2/data-privacy/erase-data-for-email-address)
  result = api_instance.purge_email_address_using_post(email_address)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling DataPrivacyApi->purge_email_address_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **email_address** | **String**| The email address. | 

### Return type

[**BaseResponse**](BaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **purge_phone_number_using_post**
> BaseResponse purge_phone_number_using_post(phone_number)

Delete the phone number, and all associated elements (/v2/data-privacy/erase-data-for-phone-number)

Given a phone number, this endpoint deletes from the Gong system any leads or contacts with a matching phone number or mobile phone number. Email messages sent to or from these leads/contacts are deleted. Calls where the leads/contacts appear are deleted. The deletion is not immediate, and may take several hours to complete.  This endpoint contains a data integrity protection mechanism to prevent the deletion of an abnormal number of objects. If the deletion fails please contact support at help@gong.io  Delete the data from your CRM and email system before performing this operation so that private data is not re-imported into Gong.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:data-privacy:delete'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::DataPrivacyApi.new
phone_number = 'phone_number_example' # String | The phone number.  This number must start with a + (plus) sign followed by the country code, area code, and local phone number. All other non-digits are ignored.  The following are examples of permitted phone numbers: +1 425 555 2671, +1-425-555-2671, +1 425 5552671, +14255552671, +1 425 555 26 71, +1(425) 555-2671, etc.  Note: This parameter should be URL-encoded.


begin
  #Delete the phone number, and all associated elements (/v2/data-privacy/erase-data-for-phone-number)
  result = api_instance.purge_phone_number_using_post(phone_number)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling DataPrivacyApi->purge_phone_number_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **phone_number** | **String**| The phone number.  This number must start with a + (plus) sign followed by the country code, area code, and local phone number. All other non-digits are ignored.  The following are examples of permitted phone numbers: +1 425 555 2671, +1-425-555-2671, +1 425 5552671, +14255552671, +1 425 555 26 71, +1(425) 555-2671, etc.  Note: This parameter should be URL-encoded. | 

### Return type

[**BaseResponse**](BaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



