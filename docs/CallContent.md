# GongAPI::CallContent

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**points_of_interest** | **BOOLEAN** | If true, add call points of interest | [optional] 
**structure** | **BOOLEAN** | If true, add call agenda, if available | [optional] 
**topics** | **BOOLEAN** | If true, add duration of call topics | [optional] 
**tracker_occurrences** | **BOOLEAN** | If true, the API will return the timing and speaker ID of each occurrence of a tracker (in addition to other tracker data). This functionality must be used in combination with the \&quot;trackers\&quot; field. The occurrence data is available only for the calls recorded since Jan 1, 2023, contact Gong support if a backfill of this data is required. | [optional] 
**trackers** | **BOOLEAN** | If true, returns smart tracker and keyword tracker information for the call. | [optional] 

