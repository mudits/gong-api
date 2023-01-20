# GongAPI::SpeechSegment

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**from_time** | **Integer** | The start time of the segment in milliseconds from the beginning of the call. | 
**party_ids** | **Array&lt;String&gt;** | The speaking parties in the segment, each must have a correlating partyId within &#x27;parties&#x27;. It is allowed to provide overlapping segments, i.e. you can either specify multiple speakers in a segment or send several overlapping segments each marked with one speaker. | 
**to_time** | **Integer** | The end time of the segment in milliseconds from the beginning of the call. | 

