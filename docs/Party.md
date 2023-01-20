# GongAPI::Party

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**affiliation** | **String** | Whether the participant is from the company or not. | [optional] 
**context** | [**Array&lt;PartyContext&gt;**](PartyContext.md) | A list of links to external systems such as CRM, Dialer, Case Management, etc. | [optional] 
**email_address** | **String** | Email address. | [optional] 
**id** | **String** | Unique ID of the participant in the call. | [optional] 
**methods** | **Array&lt;String&gt;** | Whether the participant was invited to the meeting or only attended the call. | [optional] 
**name** | **String** | The name of the participant. | [optional] 
**phone_number** | **String** | The phone number of the participant. | [optional] 
**speaker_id** | **String** | Unique ID of a participant that spoke in the call. References to this id will appear in the &#x27;/v2/calls/transcript&#x27; endpoint response. | [optional] 
**title** | **String** | The job title of the participant | [optional] 
**user_id** | **String** | The user ID of the participant within the Gong system, if the participant exists in the system. | [optional] 

