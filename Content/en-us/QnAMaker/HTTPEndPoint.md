<!-- 
NavPath: QnA Maker
LinkLabel: API Reference
Url: QnAMaker/documentation/httpendpoint
Weight: 70
-->

# API Reference #
Each published QnA Maker service is exposed as an HTTP endpoint that will take in a question and respond back with the best matched answer and a confidence score.
You need the following two GUIDs to access your knowledge base via the HTTP endpoint

  * Knowledge Base ID: This is auto-generated by the system for every published KB.
  * Subscription Key: These are assigned per account, and is used for metering. See the subscription keys section for more details.
  
## Sample Request ##

### HTTP ###
```Markdown
POST /knowledgebases/<Your KB ID>/generateAnswer HTTP/1.1
Host: qnaservice-ppe.cloudapp.net
Ocp-Apim-Subscription-Key: <Your Subscription key>
Content-Type: application/json
Cache-Control: no-cache
{"question": "Question goes here"}
```

### C# ###
```javascript
string responseString = string.Empty;

var query = “hi”; //User Query
var knowledgebaseId = “YOUR_KNOWLEDGE_BASE_ID”; // Use knowledge base id created.
var qnamakerSubscriptionKey = “YOUR_SUBSCRIPTION_KEY”; //Use subscription key assigned to you.

//Build the URI
Uri qnamakerUriBase = new Uri("https://westus.api.cognitive.microsoft.com/qnamaker/v1.0");
var builder = new UriBuilder($"{qnamakerUriBase}/knowledgebases/{knowledgebaseId}/generateAnswer");

//Add the question as part of the body
var postBody = $"{{\"question\": \"{query}\"}}";

//Send the POST request
using (WebClient client = new WebClient())
{
	//Add the subscription key header
	client.Headers.Add("Ocp-Apim-Subscription-Key", qnamakerSubscriptionKey);
	client.Headers.Add("Content-Type", "application/json");
	responseString = client.UploadString(builder.Uri, postBody);
}
```

## Sample Response ##
The response to the above request will be a JSON with the answer and the confidence score (0-100).

### JSON ###
`{
  "Answer": "Sample response",
  "Score": "0"
}`

### C# ###
```javascript
using Newtonsoft.Json; 

private class QnAMakerResult
{
    /// <summary>
    /// The top answer found in the QnA Service.
    /// </summary>
    [JsonProperty(PropertyName = "answer")]
    public string Answer { get; set; }

    /// <summary>
    /// The score in range [0, 100] corresponding to the top answer found in the QnA    Service.
    /// </summary>
    [JsonProperty(PropertyName = "score")]
    public double Score { get; set; }
}
//De-serialize the response
QnAMakerResult response;
try
{
    response = JsonConvert.DeserializeObject< QnAMakerResult >(responseString);
}
catch
{
    throw new Exception("Unable to deserialize QnA Maker response string.");
}
```
