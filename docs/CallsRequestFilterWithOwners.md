# GongAPI::CallsRequestFilterWithOwners

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**call_ids** | **Object** | List of calls Ids to be filtered. If not supplied, returns all calls between fromDateTime and toDateTime. | [optional] 
**from_date_time** | **String** | The date from which to list calls, in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC); if not specified, the calls start with the earliest recorded call. The date applies to call start time. | [optional] 
**primary_user_ids** | **Object** | An optional list of user identifiers, if supplied the API will return only the calls hosted by the specified users. The identifiers in this field match the primaryUserId field of the calls. | [optional] 
**to_date_time** | **String** | The date until which to list calls, in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC); if not specified, the calls end with the latest recorded call. The date applies to call start time. | [optional] 
**workspace_id** | **String** | Optional Workspace identifier, if supplied the API will return only the calls belonging to this workspace. | [optional] 

