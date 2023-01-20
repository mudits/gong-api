# GongAPI::Comment

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**audio_end_time** | **Float** | The number of seconds from the beginning of the call that the comment ends refers to. | [optional] 
**audio_start_time** | **Float** | The number of seconds from the beginning of the call that the comment start refers to. | [optional] 
**comment** | **String** | The comment itself. The comment may contains person tagging in this format @[user name](user Id) | [optional] 
**commenter_user_id** | **String** | Unique identifier of the user who wrote the comment. | [optional] 
**during_call** | **BOOLEAN** | True if the comment was written during the call, false if it was posted after the call. | [optional] 
**id** | **String** | Unique identifier of the comment within the Gong&#x27;s system. | [optional] 
**in_reply_to** | **String** | The unique identifier of the original comment in case the current comment is a reply to the original one. | [optional] 
**posted** | **String** | The date and time in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC); in which the comment was posted. | [optional] 

