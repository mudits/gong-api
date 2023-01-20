# GongAPI::CallParticipant

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**context** | [**Array&lt;PartyUploadContext&gt;**](PartyUploadContext.md) | A list of links to external systems such as CRM, Telephony System, Case Management, etc. | [optional] 
**email_address** | **String** | The email address of the party, if available. | [optional] 
**media_channel_id** | **Integer** | The audio channel corresponding to the company team member (rep) used when the uploaded media file is multi-channel (stereo). The channel id is either 0 or 1 (representing left or right respectively) | [optional] 
**name** | **String** | The name of the party, if available. | [optional] 
**party_id** | **String** | An identifier that is only required when speakersTimeline is provided.  The partyId is used to recognize the speakers within the provided speakersTimeline. | [optional] 
**phone_number** | **String** | The phone number of the party, if available. | [optional] 
**user_id** | **String** | The user ID of the participant within the Gong system, if the participant is a user. | [optional] 

