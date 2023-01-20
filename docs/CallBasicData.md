# GongAPI::CallBasicData

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**client_unique_id** | **String** | The call&#x27;s unique identifier in the origin recording system (typically a telephony recording system). The identifier is provided to Gong during the call creation via the Public API or through telephony systems integrations. | [optional] 
**custom_data** | **String** | Metadata as was provided to Gong during the call creation via the Public API. | [optional] 
**direction** | **String** | Call direction. | [optional] 
**duration** | **Integer** | The duration of the call, in seconds. | [optional] 
**id** | **String** | Gong&#x27;s unique numeric identifier for the call (up to 20 digits). | [optional] 
**is_private** | **BOOLEAN** | If the call is private. | [optional] 
**language** | **String** | The language codes (as defined by ISO-639-2B). E.g., eng, fre, spa, ger, and ita. Also used are und (unsupported language), and zxx (not enough speech content for identification). | [optional] 
**media** | **String** | Media type | [optional] 
**meeting_url** | **String** | The meeting provider URL on which the web conference was recorded. | [optional] 
**primary_user_id** | **String** | The primary user ID of the team member who hosted the call. | [optional] 
**purpose** | **String** | The purpose of the call. | [optional] 
**scheduled** | **String** | Scheduled date and time of the call in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | [optional] 
**scope** | **String** | The scope of the call: &#x27;internal&#x27; if all the participants are from the company, &#x27;external&#x27; if some participants are not from the company, or &#x27;unknown&#x27; if the scope is unknown. | [optional] 
**sdr_disposition** | **String** | The SDR disposition of the call | [optional] 
**started** | **String** | The date and time when the call was recorded in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC). | [optional] 
**system** | **String** | The system with which the call was carried out (e.g., WebEx, ShoreTel, etc.). | [optional] 
**title** | **String** | The title of the call. | [optional] 
**url** | **String** | The URL to the page in the Gong web application where the call is available. | [optional] 
**workspace_id** | **String** | Gong&#x27;s unique numeric identifier for the call&#x27;s workspace (up to 20 digits). | [optional] 

