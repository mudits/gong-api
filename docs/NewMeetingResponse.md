# GongAPI::NewMeetingResponse

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**additional_invitees** | [**Array&lt;MeetingInvitee&gt;**](MeetingInvitee.md) | Attendees the requesting party should add to the invitation, this should support adding email addresses such as coordinator@gong.io for Gong to schedule the recording of the meeting. | [optional] 
**meeting_id** | **String** | Gong&#x27;s unique identifier for the meeting (up to 20 digits). | [optional] 
**meeting_url** | **String** | The Gong URL of the meeting, should be used to enter the meeting. | [optional] 
**request_id** | **String** | A Gong request reference Id, generated for this request. Can be used for troubleshooting purposes. | [optional] 

