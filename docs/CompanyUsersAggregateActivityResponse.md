# GongAPI::CompanyUsersAggregateActivityResponse

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**from_date_time** | **String** | The date and time in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC), when the list of results starts. | [optional] 
**records** | [**Records**](Records.md) |  | [optional] 
**request_id** | **String** | A Gong request reference Id, generated for this request. Can be used for troubleshooting purposes. | [optional] 
**time_zone** | **String** | The company&#x27;s defined timezone in Gong. | [optional] 
**to_date_time** | **String** | The date and time in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC), when the list of results ends. | [optional] 
**users_aggregate_activity_stats** | [**Array&lt;UserActivity&gt;**](UserActivity.md) | A list, in which each item specifies one user&#x27;s activities. | [optional] 

