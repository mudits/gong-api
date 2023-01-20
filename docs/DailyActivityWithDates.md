# GongAPI::DailyActivityWithDates

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**calls_as_host** | **Object** | List of IDs of calls in which this user is the host. | [optional] 
**calls_attended** | **Object** | List of IDs of calls in which this user is participant (not host) | [optional] 
**calls_comments_given** | **Object** | List of IDs of calls in which a user gave at least one comment. | [optional] 
**calls_comments_received** | **Object** | List of IDs of calls in which a user received at least one comment on the users calls. | [optional] 
**calls_gave_feedback** | **Object** | List of IDs of calls where the user gave feedback. | [optional] 
**calls_marked_as_feedback_given** | **Object** |  List of IDs of calls in which someone pressed the \&quot;Mark as reviewed\&quot;. | [optional] 
**calls_marked_as_feedback_received** | **Object** | List of IDs of calls in which someone pressed the \&quot;Mark as reviewed\&quot; on the users calls. | [optional] 
**calls_received_feedback** | **Object** |  List of IDs of calls where the user received feedback. | [optional] 
**calls_requested_feedback** | **Object** |  List of IDs of calls where the user requested feedback. | [optional] 
**calls_scorecards_filled** | **Object** | List of IDs of calls in which the user filled scorecards. | [optional] 
**calls_scorecards_received** | **Object** | List of IDs of calls in which someone filled a scorecard on the users calls. | [optional] 
**calls_shared_externally** | **Object** | List of IDs of calls the user shared with people outside the company. | [optional] 
**calls_shared_internally** | **Object** | List of IDs of calls the user shared with other users inside the company. | [optional] 
**from_date** | **String** | The start of the day in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | [optional] 
**others_calls_listened_to** | **Object** | List of IDs of calls, not belonging to this user, that the user listened to. | [optional] 
**own_calls_listened_to** | **Object** | List of IDs of the user&#x27;s own calls, that the user listened to. | [optional] 
**to_date** | **String** | The end of the day in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | [optional] 

