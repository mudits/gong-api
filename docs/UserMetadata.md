# GongAPI::UserMetadata

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**active** | **BOOLEAN** | True if the user is active, false if not. | [optional] 
**created** | **String** | Creation time in the ISO-8601 format (e.g., &#x27;2018-02-18T02:30:00-07:00&#x27; or &#x27;2018-02-18T08:00:00Z&#x27;, where Z stands for UTC);of the Gong user. | [optional] 
**email_address** | **String** | The email address of the Gong user. | [optional] 
**email_aliases** | **Object** | List of email address aliases of the Gong user. | [optional] 
**extension** | **String** | The extension number of the Gong user. | [optional] 
**first_name** | **String** | The first name of the Gong user. | [optional] 
**id** | **String** | Gong&#x27;s unique numeric identifier for the user (up to 20 digits). | [optional] 
**last_name** | **String** | The last name of the Gong user. | [optional] 
**manager_id** | **String** | The manager ID of the Gong user. | [optional] 
**meeting_consent_page_url** | **String** | The Gong recording consent meeting link | [optional] 
**personal_meeting_urls** | **Object** | The list of personal meeting URLs of the Gong user. | [optional] 
**phone_number** | **String** | The phone number of the Gong user. | [optional] 
**settings** | [**Settings**](Settings.md) |  | [optional] 
**spoken_languages** | [**Array&lt;SpokenLanguage&gt;**](SpokenLanguage.md) |  | [optional] 
**title** | **String** | The job title of the Gong user. | [optional] 

