# GongAPI::PhoneNumberReferences

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**calls** | [**Array&lt;CallReference&gt;**](CallReference.md) | Related calls. | [optional] 
**customer_data** | [**Array&lt;CustomerData&gt;**](CustomerData.md) | A list of links to data from external systems (such as CRM, Telephony System, Case Management, etc.) that reference the email address and that Gong stores. | [optional] 
**email_addresses** | **Array&lt;String&gt;** | Related email addresses. | [optional] 
**emails** | [**Array&lt;EmailMessage&gt;**](EmailMessage.md) | Related email messages. | [optional] 
**matching_phone_numbers** | **Array&lt;String&gt;** | Matching phone numbers found. | [optional] 
**meetings** | [**Array&lt;Meeting&gt;**](Meeting.md) | Related meetings. | [optional] 
**request_id** | **String** | A Gong request reference Id, generated for this request. Can be used for troubleshooting purposes. | [optional] 
**supplied_phone_number** | **String** | The supplied phone number. | [optional] 

