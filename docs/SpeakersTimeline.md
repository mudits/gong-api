# GongAPI::SpeakersTimeline

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**precise** | **BOOLEAN** | Indicates whether the provided speech segments match the media precisely or need further refinement based on the media. \&quot;Precisely\&quot; here means that segments do not deviate from the actual speech in the media by more than 100ms. | [optional] 
**speech_segments** | [**Array&lt;SpeechSegment&gt;**](SpeechSegment.md) | The audio recording speech segments (who spoke when).  | [optional] 

