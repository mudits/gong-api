# GongAPI::StatsApi

All URIs are relative to *//127.0.0.1/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**list_answered_scorecards_using_post**](StatsApi.md#list_answered_scorecards_using_post) | **POST** /v2/stats/activity/scorecards | Retrieve answered scorecards for applicable reviewed users or scorecards for a date range (/v2/stats/activity/scorecards)
[**list_interaction_stats_using_post**](StatsApi.md#list_interaction_stats_using_post) | **POST** /v2/stats/interaction | Retrieve interaction stats for applicable users by date (/v2/stats/interaction)
[**list_multiple_users_aggregate_activity_using_post**](StatsApi.md#list_multiple_users_aggregate_activity_using_post) | **POST** /v2/stats/activity/aggregate | Retrieve aggregated activity for defined users by date (/v2/stats/activity/aggregate)
[**list_multiple_users_aggregate_by_period_using_post**](StatsApi.md#list_multiple_users_aggregate_by_period_using_post) | **POST** /v2/stats/activity/aggregate-by-period | Retrieve aggregated activity for defined users by a date range with grouping in time periods (/v2/stats/activity/aggregate-by-period)
[**list_multiple_users_day_by_day_activity_using_post**](StatsApi.md#list_multiple_users_day_by_day_activity_using_post) | **POST** /v2/stats/activity/day-by-day | Retrieve daily activity for applicable users for a date range (/v2/stats/activity/day-by-day)

# **list_answered_scorecards_using_post**
> AnsweredScorecards list_answered_scorecards_using_post(body)

Retrieve answered scorecards for applicable reviewed users or scorecards for a date range (/v2/stats/activity/scorecards)

Retrieve all the answers for the scorecards that were reviewed during a specified date range, for calls that took place during a specified date range, for specific scorecards or for specific reviewed users.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:stats:scorecards'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::StatsApi.new
body = GongAPI::RequestAnsweredScorecardsFilter.new # RequestAnsweredScorecardsFilter | answeredScorecardsRequest


begin
  #Retrieve answered scorecards for applicable reviewed users or scorecards for a date range (/v2/stats/activity/scorecards)
  result = api_instance.list_answered_scorecards_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling StatsApi->list_answered_scorecards_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**RequestAnsweredScorecardsFilter**](RequestAnsweredScorecardsFilter.md)| answeredScorecardsRequest | 

### Return type

[**AnsweredScorecards**](AnsweredScorecards.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **list_interaction_stats_using_post**
> CompanyUsersIntercationStatsResponse list_interaction_stats_using_post(body)

Retrieve interaction stats for applicable users by date (/v2/stats/interaction)

Returns interaction stats for users based on calls that have Whisper turned on.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:stats:interaction'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::StatsApi.new
body = GongAPI::RequestMultipleUsersWithDates.new # RequestMultipleUsersWithDates | statsRequest


begin
  #Retrieve interaction stats for applicable users by date (/v2/stats/interaction)
  result = api_instance.list_interaction_stats_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling StatsApi->list_interaction_stats_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**RequestMultipleUsersWithDates**](RequestMultipleUsersWithDates.md)| statsRequest | 

### Return type

[**CompanyUsersIntercationStatsResponse**](CompanyUsersIntercationStatsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **list_multiple_users_aggregate_activity_using_post**
> CompanyUsersAggregateActivityResponse list_multiple_users_aggregate_activity_using_post(body)

Retrieve aggregated activity for defined users by date (/v2/stats/activity/aggregate)

Lists the activity of multiple users within the Gong system during a defined period. Given the period, this endpoint returns multiple records, one for each user, with an applicable activity during the period. Each record includes statistics about the user's activity.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:stats:user-actions'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::StatsApi.new
body = GongAPI::RequestMultipleUsersWithDates.new # RequestMultipleUsersWithDates | multipleUsersRequest


begin
  #Retrieve aggregated activity for defined users by date (/v2/stats/activity/aggregate)
  result = api_instance.list_multiple_users_aggregate_activity_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling StatsApi->list_multiple_users_aggregate_activity_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**RequestMultipleUsersWithDates**](RequestMultipleUsersWithDates.md)| multipleUsersRequest | 

### Return type

[**CompanyUsersAggregateActivityResponse**](CompanyUsersAggregateActivityResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **list_multiple_users_aggregate_by_period_using_post**
> UsersAggregateByPeriodActivity list_multiple_users_aggregate_by_period_using_post(body)

Retrieve aggregated activity for defined users by a date range with grouping in time periods (/v2/stats/activity/aggregate-by-period)

Lists the aggregated activity of multiple users within the Gong system for each time period within the defined date range. This endpoint returns multiple records, one for each user. For each user there are items for every time period in the date range, including statistics about the user's activity. Records are returned only for users with activity in the range.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:stats:user-actions'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::StatsApi.new
body = GongAPI::RequestWithTimePeriodMultipleUsersWithDates.new # RequestWithTimePeriodMultipleUsersWithDates | multipleUsersRequest


begin
  #Retrieve aggregated activity for defined users by a date range with grouping in time periods (/v2/stats/activity/aggregate-by-period)
  result = api_instance.list_multiple_users_aggregate_by_period_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling StatsApi->list_multiple_users_aggregate_by_period_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**RequestWithTimePeriodMultipleUsersWithDates**](RequestWithTimePeriodMultipleUsersWithDates.md)| multipleUsersRequest | 

### Return type

[**UsersAggregateByPeriodActivity**](UsersAggregateByPeriodActivity.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **list_multiple_users_day_by_day_activity_using_post**
> UsersDayByDayActivity list_multiple_users_day_by_day_activity_using_post(body)

Retrieve daily activity for applicable users for a date range (/v2/stats/activity/day-by-day)

Retrieve the daily activity of multiple users within the Gong system for a range of dates. This endpoint returns records including statistics about each user's activity, on the daily level. Records are returned only for users with activity in the range.  When accessed through a Bearer token authorization method, this endpoint requires the scope 'api:stats:user-actions:detailed'.

### Example
```ruby
# load the gem
require 'gong_api'

api_instance = GongAPI::StatsApi.new
body = GongAPI::RequestMultipleUsersWithDates.new # RequestMultipleUsersWithDates | multipleUsersRequest


begin
  #Retrieve daily activity for applicable users for a date range (/v2/stats/activity/day-by-day)
  result = api_instance.list_multiple_users_day_by_day_activity_using_post(body)
  p result
rescue GongAPI::ApiError => e
  puts "Exception when calling StatsApi->list_multiple_users_day_by_day_activity_using_post: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**RequestMultipleUsersWithDates**](RequestMultipleUsersWithDates.md)| multipleUsersRequest | 

### Return type

[**UsersDayByDayActivity**](UsersDayByDayActivity.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



