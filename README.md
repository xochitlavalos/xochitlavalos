# Xóchitl A. Avalos

AI Cloud Engineer at **MasterControl**, where I run production AI and data systems on AWS. Before that I was a data scientist on **Apple** wearable research and a research engineer on **Google** wearable research, and I studied Cognitive Science with an AI emphasis at **UC Merced**. I care most about AI systems that keep working after launch, and about catching the failures that look like success.

## What I build at MasterControl

Most of my production work is in private company repos, so here is what it does:

- **Production AI for sales.** Runs the system behind 19 live AI products in Salesforce (call prep, risk analysis, win/loss, sales-to-CS handoff): about 1,700 nightly LLM jobs on Step Functions, Lambda, and Bedrock. After a silent failure, recovered 90% of 3,109 outputs by checking each one against Salesforce instead of trusting the run logs.
- **Enterprise LLM platform.** The company's shared access to foundation models: AWS Bedrock behind a LiteLLM gateway for model routing, OpenWebUI as the interface, and Bedrock Guardrails with automated risk detection across 6 safety categories.
- **MCP server for company data.** AWS infrastructure that lets employees query company data from Claude Code, with Okta sign-in, per-user tokens, and read-only access.
- **Change-request decision engine.** Reviews Jira database change requests across 9 projects using rules derived from 57 past tickets, and posts a recommendation to Jira and Slack in under 5 minutes. Matched human reviewers on 52 of 53 requests (98%).
- **Business system integrations.** Owns the Salesforce to NetSuite sync for accounts, contacts, and sales orders, where contact sync failures dropped 99% (about 440 to 5 a month).

## Portfolio projects

Public, rebuilt versions of the patterns above. Each one has tests that run without an AWS account.

| Project | What it does | Stack |
|---|---|---|
| [mcp-gateway-aws](https://github.com/xochitlavalos/mcp-gateway-aws) | Multi-user MCP server where each person signs in with their own identity provider account and reaches an upstream API with their own credential, never a shared token. Credentials are encrypted per user with KMS. | Python, API Gateway, Lambda, DynamoDB, KMS, AWS CDK |
| [bedrock-guardrails-openwebui](https://github.com/xochitlavalos/bedrock-guardrails-openwebui) | Open WebUI filter that checks every chat turn against Amazon Bedrock Guardrails, so one safety policy covers every model in the UI. Blocks harmful input, withholds harmful output, and masks PII. | Python, Bedrock Guardrails, Open WebUI Pipelines, CloudFormation |
| [llm-contract-extractor](https://github.com/xochitlavalos/llm-contract-extractor) | Pulls key terms out of contracts with Bedrock. Every value must come with a verbatim quote from the document, and anything that can't be found is rejected and flagged for review. Includes an eval against labeled samples. | Python, Bedrock Converse, Lambda, S3, DynamoDB, SQS, AWS CDK |
| [lambda-fleet-auditor](https://github.com/xochitlavalos/lambda-fleet-auditor) | Read-only audit of every Lambda function across all regions: outdated runtimes, functions nobody calls, events that can silently disappear, public endpoints, and config drift since the last scan. | Python, boto3, CloudWatch, S3, SNS, AWS CDK |

## Tools

Python · SQL · R · AWS (Bedrock, Lambda, Step Functions, EventBridge, API Gateway, DynamoDB, KMS) · AWS CDK · LiteLLM · MCP · RAG · Salesforce · NetSuite · n8n

[LinkedIn](https://www.linkedin.com/in/xochitl-a-avalos)
