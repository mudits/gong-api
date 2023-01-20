# GongAPI::EmailAddressReferences

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**calls** | [**Array&lt;CallReference&gt;**](CallReference.md) | Related calls. | [optional] 
**customer_data** | [**Array&lt;CustomerData&gt;**](CustomerData.md) | A list of links to data from external systems (such as CRM, Telephony System, Case Management, etc.) that reference the email address and that Gong stores. | [optional] 
**customer_engagement** | [**Array&lt;CustomerEngagement&gt;**](CustomerEngagement.md) | A list of customer&#x27;s engagement (such as viewing external share call) | [optional] 
**emails** | [**Array&lt;EmailMessage&gt;**](EmailMessage.md) | Related email messages. | [optional] 
**meetings** | [**Array&lt;Meeting&gt;**](Meeting.md) | Related meetings. | [optional] 
**request_id** | **String** | A Gong request reference Id, generated for this request. Can be used for troubleshooting purposes. | [optional] 

