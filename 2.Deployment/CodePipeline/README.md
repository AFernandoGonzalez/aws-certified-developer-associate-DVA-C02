# AWS CodePipeline Cheat Sheet

## Overview
AWS CodePipeline is a fully managed continuous delivery service that helps automate the build, test, and deploy phases of your release process every time there is a code change.

## Use Cases
- Automate release pipelines
- Integrate with other AWS services and third-party tools
- Implement continuous integration and continuous delivery (CI/CD)
- Enable fast and reliable application updates

## Key Features
- **Pipeline**: A workflow consisting of stages and actions.
- **Stages**: Logical units in a pipeline (e.g., Source, Build, Test, Deploy).
- **Actions**: Tasks performed in a stage (e.g., source retrieval, build, test, deploy).
- **Transitions**: Enable or disable transitions between stages.
- **Artifacts**: Output of one stage that can be input for another stage.

## Key Concepts

### Pipelines
- **Structure**: Pipelines are composed of stages, and each stage can have multiple actions.
- **Execution**: Pipelines automatically trigger when changes are detected.

### Stages
- **Source Stage**: Retrieves the source code from repositories like S3, CodeCommit, GitHub.
- **Build Stage**: Compiles source code using services like CodeBuild or third-party build tools.
- **Test Stage**: Runs tests using CodeBuild or other testing tools.
- **Deploy Stage**: Deploys the application using services like CodeDeploy, ECS, Lambda, or third-party deployment tools.

### Actions
- **Source Action**: Fetches source code.
- **Build Action**: Builds and packages the application.
- **Test Action**: Executes tests on the built application.
- **Deploy Action**: Deploys the application to the target environment.
- **Approval Action**: Manual approval step before proceeding to the next stage.

### Transitions
- **Enable/Disable**: Control the flow between stages by enabling or disabling transitions.

### Artifacts
- **Input Artifacts**: Artifacts required for a stage to run.
- **Output Artifacts**: Artifacts produced by a stage that can be used by subsequent stages.

## Security
- **IAM Roles**: Define permissions for CodePipeline to access AWS resources.
- **Encryption**: Use AWS KMS to encrypt pipeline artifacts.
- **Approval Actions**: Implement manual approval steps to enforce security reviews.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor pipeline success rates, duration, and failure rates.
- **CloudWatch Logs**: Log pipeline activities for monitoring and troubleshooting.
- **Notifications**: Integrate with SNS to receive notifications on pipeline status.

## Pricing
- Based on the number of active pipelines and their execution frequency.

## Key Terms
- **Pipeline**: A workflow consisting of stages and actions to automate the release process.
- **Stage**: A logical unit within a pipeline, consisting of one or more actions.
- **Action**: A task performed within a stage (e.g., source, build, test, deploy).
- **Artifact**: Output of one stage that can be used as input for another stage.
- **Transition**: Control flow between stages.

## Best Practices
- **Use Multiple Stages**: Break down the pipeline into logical stages for better management.
- **Monitor Pipelines**: Use CloudWatch Metrics and Logs to monitor pipeline performance and troubleshoot issues.
- **Secure IAM Roles**: Ensure IAM roles have the least privilege required.
- **Implement Approval Actions**: Add manual approval steps for critical stages.
- **Automate Testing**: Integrate automated tests to ensure application quality.
- **Version Control Integration**: Connect pipelines to version control systems like CodeCommit, GitHub, or Bitbucket.

