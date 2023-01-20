# GongAPI::Tracker

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **Integer** | The number of times words in this Tracker occurred in the call. | [optional] 
**id** | **String** | The unique ID of the Tracker. | [optional] 
**name** | **String** | The name of the Tracker (e.g., Stores). | [optional] 
**occurrences** | [**Array&lt;Occurrences&gt;**](Occurrences.md) | A list of details for each occurrence of Tracker phrases. | [optional] 
**phrases** | [**Array&lt;TrackerPhrases&gt;**](TrackerPhrases.md) | A list of occurrence counters for each specific phrase within the tracker (e.g., Amazon, Walmart). | [optional] 
**type** | **String** | The type of the tracker - Keyword or Smart. | [optional] 

