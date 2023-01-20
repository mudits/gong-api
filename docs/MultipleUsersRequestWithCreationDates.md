# GongAPI::MultipleUsersRequestWithCreationDates

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**created_from_date_time** | **String** | An optional user creation time lower limit, if supplied the API will return only the users created at or after this time. The filed is in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | [optional] 
**created_to_date_time** | **String** | An optional user creation time upper limit, if supplied the API will return only the users created before this time. The filed is in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | [optional] 
**include_avatars** | **BOOLEAN** | Avatars are synthetic users representing Gong employees (CSMs and support providers) when they access your instance. References to avatars&#x27; IDs may be found in the outputs of other API endpoints. This parameter is optional, if not provided avatars will not be included in the results. | [optional] 
**user_ids** | **Object** | Set of Gong&#x27;s unique numeric identifiers for the users (up to 20 digits). | [optional] 

