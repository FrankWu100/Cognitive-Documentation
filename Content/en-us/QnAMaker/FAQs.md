<!-- 
NavPath: QnA Maker
LinkLabel: FAQ
Url: QnAMaker/documentation/faqs
Weight: 60
-->

# FAQs #
### Who are the target audience for the QnA Maker tool?
QnA Maker is primarily meant to provide a FAQ data source which you can query from your Bot/Application. Although developers will find this useful, content owners will especially benefit from this tool. QnA Maker is a completely no-code way of managing the content that powers your Bot/Application.

### How do I login to the QnA Maker Portal?
You can login with your [Microsoft account](https://www.microsoft.com/en-us/account/).

### Is the QnA Maker Service free?
Yes, currently the QnA Maker tool is free to use. However, we do meter the usage per account. See the Subscription Keys section of the documentation for details.

### My URLs have valid FAQ content, but the tool cannot extract them. Why not?
It’s possible that the tool is not able to auto-extract QnA from valid FAQ URLs. In such cases, you have an option to copy-paste the QnA content in a txt and try ingesting it. Alternately, you can always editorially add content to your knowledge base.

### What format does the tool expect the file content to be?
We support two formats of files for ingestion.

	1.	.tsv: QnA contained in the format Question<Tab>Answer
	2.	.txt, .docx, .pdf: QnA contained as regular FAQ content, i.e. sequence of questions and answers.
	
### How large a knowledge base can I create?
Currently we have a limit of a 20MB knowledge base.

### The updates I made to my knowledge base are not reflected on publish. Why not?
Every edit operation, whether in Table update, Test or Settings needs to be saved before it can be published. Make sure you press the Save and retrain button after every edit operation.

### What is the roadmap of the QnA Maker?
Currently the QnA Maker tool handles semi-structured FAQ content. Eventually the vision is to be able to answer questions from un-structured content as well.

### Do I need to use Bot Framework in order to use QnA Maker?
No, you don’t. However, QnA Maker is offered as one of several templates in [Azure Bot Service](https://azure.microsoft.com/services/bot-service/) which enables rapid intelligent bot development powered by Microsoft Bot Framework, and run in a serverless environment. Bots scale based on demand; pay only for the resources you consume.

### Why can’t I replace my Knowledge Base with the upload feature?
The format in which upload expects the file is, tab separated columns of Question, Answer and Source.

### When should I refresh my subscription keys?
You should refresh your subscription keys if you suspect that they have been compromised. Any requests with your subscription key will count towards your quota.

### How safe is my knowledge base data?
Every knowledge base content is stored in Azure storage by the QnAMaker tool. You need a combination of knowledge base id and subscription key to access the knowledge base. The knowledge base contents are not used by the tool for any other purpose.

### Does the KB support rich data?
The knowledge base supports Markdown. However, the auto-extraction from URLs has limited HTML to Markdown conversion capability. If you want to use full-fledged Markdown, you can modify your content directly in the Table, or upload a KB with the rich content. 

