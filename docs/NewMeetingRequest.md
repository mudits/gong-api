# GongAPI::NewMeetingRequest

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**end_time** | **String** | The meeting end time in ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | [optional] 
**external_id** | **String** | The ID as it is formed on the external system. | [optional] 
**invitees** | [**Array&lt;MeetingInvitee&gt;**](MeetingInvitee.md) | A list of email addresses of invitees to the event (not including the organizer). | 
**organizer_email** | **String** | The email address of the user creating the meeting, the Gong consent page link will be used according to the settings of this user. | [optional] 
**start_time** | **String** | The meeting start time in ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | [optional] 
**title** | **String** | Title of the event. | [optional] 

