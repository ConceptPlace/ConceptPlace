<div align="center">
  <h1>MARK AI Backend</h1>
  <p><strong>Serverless foundations for the Concept Place marketing workspace.</strong></p>
  <p>
    <img src="https://img.shields.io/badge/AWS-SAM-FF9900?style=flat-square&logo=amazonaws&logoColor=white" alt="AWS SAM" />
    <img src="https://img.shields.io/badge/AWS-Lambda-FF9900?style=flat-square&logo=awslambda&logoColor=white" alt="AWS Lambda" />
    <img src="https://img.shields.io/badge/Amazon-API%20Gateway-FF4F8B?style=flat-square&logo=amazonapigateway&logoColor=white" alt="Amazon API Gateway" />
    <img src="https://img.shields.io/badge/Python-3-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python 3" />
  </p>
  <p><a href="https://www.conceptplace.in/">Visit Concept Place →</a></p>
</div>

---

## Overview

mark-ai-backend contains the source code and supporting files for a serverless application built with the AWS Serverless Application Model (SAM) CLI. It provides the backend foundation for MARK AI and Concept Place workflows, using AWS Lambda functions behind an Amazon API Gateway API.

The project is structured so the application can be built, tested, run locally, and deployed through the same SAM workflow. Infrastructure is declared in template.yaml, keeping the cloud resources and application code close together.

## Architecture

```text
Client or workflow
       │
       ▼
Amazon API Gateway
       │
       ▼
AWS Lambda functions
       │
       ▼
Application services and AWS resources
```

The AWS resources are defined in template.yaml. When the template changes, the same deployment process updates the infrastructure alongside the application code.

## Repository structure

| Path | Purpose |
| --- | --- |
| hello_world/ | Source code for the application's Lambda function. |
| events/ | Sample invocation events for local Lambda testing. |
| tests/ | Unit and integration tests. |
| template.yaml | SAM template defining the application's AWS resources. |
| samconfig.toml | Optional saved deployment configuration created by SAM. |

## Prerequisites

Before building or deploying the application, install the following tools:

- [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)
- [Python 3](https://www.python.org/downloads/)
- [Docker Community Edition](https://hub.docker.com/search/?type=edition&offering=community)
- An AWS account with credentials configured for the target environment

### Optional IDE support

The [AWS Toolkit](https://aws.amazon.com/tools/) adds SAM-aware development and debugging workflows to popular IDEs, including VS Code, Visual Studio, and JetBrains IDEs such as IntelliJ IDEA, PyCharm, WebStorm, GoLand, Rider, and DataGrip.

## Quick start

Build and deploy for the first time:

```bash
sam build --use-container
sam deploy --guided
```

sam build --use-container installs the dependencies defined in hello_world/requirements.txt, creates a deployment package, and writes build artifacts to .aws-sam/build.

sam deploy --guided packages and deploys the stack, then walks through the configuration that defines how it will run in AWS.

## Deployment configuration

During the guided deployment, SAM asks for the configuration needed to create or update the stack.

| Setting | What it controls |
| --- | --- |
| **Stack name** | The CloudFormation stack name. Use a name that is unique within the AWS account and Region. |
| **AWS Region** | The Region where the stack is deployed. |
| **Confirm changes before deploy** | Whether SAM shows a change set for review before applying it. |
| **Allow SAM CLI IAM role creation** | Allows SAM to create the IAM roles required by the Lambda resources. This requires the CAPABILITY_IAM capability. |
| **Save arguments to samconfig.toml** | Saves the selected deployment settings so later deployments can run with fewer prompts. |

After deployment, the API Gateway endpoint URL is available in the CloudFormation stack outputs.

## Run and test locally

### Invoke a single function

Sample events in events/ can be passed directly to a Lambda function:

```bash
sam local invoke HelloWorldFunction --event events/event.json
```

### Start the local API

Use SAM to emulate the API Gateway routes and invoke the local Lambda functions:

```bash
sam local start-api
curl http://localhost:3000/
```

The route configuration is declared in template.yaml:

```yaml
Events:
  HelloWorld:
    Type: Api
    Properties:
      Path: /hello
      Method: get
```

## Add AWS resources

AWS SAM extends AWS CloudFormation with a simpler syntax for common serverless resources, including functions, events, and APIs. Add or change the relevant resources in template.yaml, then rebuild and deploy using the same workflow.

For resources outside the SAM specification, standard [AWS CloudFormation resource types](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html) can be included in the template.

## Logs and troubleshooting

Use sam logs to fetch, tail, and filter logs from deployed Lambda functions:

```bash
sam logs -n HelloWorldFunction --stack-name "mark-ai-backend" --tail
```

This command works with AWS Lambda functions generally, not only functions deployed through SAM. For more examples, see the [SAM CLI logging documentation](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-logging.html).

## Tests

Install the test dependencies and run the test suites with pytest:

```bash
pip install -r tests/requirements.txt --user

# Unit tests
python -m pytest tests/unit -v

# Integration tests (after deployment)
AWS_SAM_STACK_NAME="mark-ai-backend" python -m pytest tests/integration -v
```

Integration tests require the AWS_SAM_STACK_NAME environment variable to match the deployed stack.

## Cleanup

When the stack is no longer needed, delete it using the AWS CLI:

```bash
sam delete --stack-name "mark-ai-backend"
```

## Resources

- [AWS SAM Developer Guide](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/what-is-sam.html)
- [AWS SAM specification](https://github.com/awslabs/serverless-application-model/blob/master/versions/2016-10-31.md)
- [AWS Serverless Application Repository](https://aws.amazon.com/serverless/serverlessrepo/)
- [Concept Place](https://www.conceptplace.in/)

---

<p align="center">Built for reliable serverless workflows behind MARK AI.</p>
