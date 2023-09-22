# Automate your Infrastructure
One of the role of data engineers is to deploy data pipeline using cloud service provide like GCP, AWS. Considering AWS as an example, we may want to use API Gateway as our representational state transfer (REST) interface to perform data ingestion, a few Lambda functions to validate the ingestion, Kinesis Data Streams to pro‐ vide a real-time analysis, Kinesis Data Firehose to deliver the data, and Sim‐ ple Storage Service (S3) as a persistence layer. We may also want to use Athena as a visualization layer.

Then six components can be setud using web console easily and it will not take so much time. But if more pipelines are integreated, doing the same thing again and again will kill much time. Better approach to resolve this is to pick a tool like (Terraform) and write code to maintain infra. 

Here is some guidelines:
1. **Never use web console:**
Choose IaC (Infra as Code) tool to do that. 

2. **Make it modular:**
For example, use one module to deploy your API gateway, another mod‐ ule to deploy Kinesis, an additional module to manage IAM roles, and so forth. Most tools allow you to reuse your code in various components (for example, sharing IAM policies to write only once and use every‐ where).

3. **Use version control system to manage code:**
It's helpful to work as team and collaborate and enable to check code before merging with master branch. 

4. **Test code before apply:**
For example, Terraform allows to show the changes before applying them. 

5. **Use CI/CD to deliver pipeline**:
You can make everything automate by using CI/CD pipeline.

If any of items is missing, spend time on it. It will be worthy to spend time on it.   
