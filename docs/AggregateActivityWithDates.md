# GongAPI::AggregateActivityWithDates

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**calls_as_host** | **Integer** | The number of recorded calls this user hosted. | [optional] 
**calls_attended** | **Integer** | The number of calls in which this user is participant (not host). | [optional] 
**calls_comments_given** | **Integer** | The number of calls in which a user gave at least one comment. | [optional] 
**calls_comments_received** | **Integer** | The number of calls in which a user received at least one comment on the users calls. | [optional] 
**calls_gave_feedback** | **Integer** | The number of recorded calls the user gave feedback on. | [optional] 
**calls_marked_as_feedback_given** | **Integer** | The number of calls in which someone pressed the \&quot;Mark as reviewed\&quot;. | [optional] 
**calls_marked_as_feedback_received** | **Integer** | The number of calls in which someone pressed the “Mark as reviewed” on the users calls. | [optional] 
**calls_received_feedback** | **Integer** | The number of recorded calls the user received feedback on. | [optional] 
**calls_requested_feedback** | **Integer** | The number of recorded calls the user requested feedback on. | [optional] 
**calls_scorecards_filled** | **Integer** | The number of scorecards the user completed. | [optional] 
**calls_scorecards_received** | **Integer** | The number of calls in which someone filled a scorecard on the user&#x27;s calls. | [optional] 
**calls_shared_externally** | **Integer** | The number of calls the user shared with others outside the company. | [optional] 
**calls_shared_internally** | **Integer** | The number of calls the user shared with others inside the company. | [optional] 
**from_date** | **String** | The start of the period, or the request filter&#x27;s fromDate for the first period in the range, in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | [optional] 
**others_calls_listened_to** | **Integer** | The number of other users&#x27; calls the user listened to. | [optional] 
**own_calls_listened_to** | **Integer** | The number of the user&#x27;s own calls the user listened to. | [optional] 
**to_date** | **String** | The end of the period, or the request filter&#x27;s toDate for the last period in the range,  in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | [optional] 

