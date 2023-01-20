# GongAPI::RegisterGenericCrmResponse

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**integration_id** | **Integer** | &lt;style&gt;.public-api-info {    background: rgb(222, 235, 255);}.public-api-tip {    background: rgb(227, 252, 239);}.public-api-parameter {    background: rgba(9,30,66,0.08);}.public-api-note {    background: rgb(234, 230, 255);}.public-api-important {    background: rgb(255, 250, 230);}.public-api-critical {    background: rgb(255, 235, 230);}table, th, td {  border: 1px solid gray;  border-collapse: collapse;}th, td {  padding: 5px;}th {  text-align: left;}&lt;/style&gt;Use the Gong integration ID in future requests to the API. This ensures you are accessing the correct integration. &lt;br&gt;&lt;div class&#x3D;&#x27;public-api-tip&#x27;&gt;You will need a library that can parse the &lt;code class&#x3D;&#x27;public-api-parameter&#x27;&gt;integrationId&lt;/code&gt; in the response as Long or BigInt. Parsing the &lt;code class&#x3D;&#x27;public-api-parameter&#x27;&gt;integrationId&lt;/code&gt; as an Integer will truncate the &lt;code class&#x3D;&#x27;public-api-parameter&#x27;&gt;integrationId&lt;/code&gt; to trailing zeros and will return an incorrect id.&lt;/div&gt; | [optional] 
**request_id** | **String** | A Gong request reference Id, generated for this request. Can be used for troubleshooting purposes. | [optional] 

