# AWS CodeBuild Cheat Sheet

## Overview
AWS CodeBuild is a fully managed continuous integration service that compiles source code, runs tests, and produces software packages that are ready to deploy.

## Use Cases
- Continuous Integration (CI)
- Automated Testing
- Build Automation
- Multi-Language Build Support

## Key Features
- **Build Projects**: Define how CodeBuild will run a build.
- **Build Environments**: Docker images used to run the build.
- **Buildspec File**: YAML file that defines the build commands and settings.
- **Artifacts**: Output files of the build process.
- **Reports**: Test results and other build-related reports.

## Key Concepts

### Build Projects
- **Project Name**: The unique name of the build project.
- **Source**: Where the source code is stored (e.g., S3, GitHub, CodeCommit).
- **Environment**: Specifies the runtime environment for the build.
- **Service Role**: IAM role that grants CodeBuild permissions to access AWS resources.
- **Artifacts**: Defines where to store the output of the build process.
- **Buildspec**: File containing build commands and related settings.

### Build Environments
- **Compute Types**: Specify the compute resources used for the build (e.g., small, medium, large).
- **Environment Images**: Docker images that provide the runtime environment for the build.

### Buildspec File
- **version**: The version of the buildspec format.
- **phases**: Different phases of the build process (install, pre_build, build, post_build).
- **artifacts**: Specify the files to be uploaded as build artifacts.
- **reports**: Define test reports.

## Security
- **IAM Roles**: Define permissions for CodeBuild to access AWS resources.
- **VPC Integration**: Run builds in an Amazon VPC to access resources that are not publicly accessible.
- **Encryption**: Artifacts can be encrypted using AWS KMS.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor build success rates, duration, and failure rates.
- **CloudWatch Logs**: Log data from CodeBuild for monitoring and troubleshooting.
- **Notifications**: Integrate with SNS to receive notifications on build status.

## Pricing
- Based on the compute time used for the build and the compute type selected.

## Key Terms
- **Build Project**: Defines how CodeBuild will run a build.
- **Build Environment**: Docker image used to run the build.
- **Buildspec File**: YAML file that defines build commands and settings.
- **Artifacts**: Output files of the build process.
- **Reports**: Test results and other build-related reports.

## Best Practices
- **Use Buildspec Files**: Define all build commands and settings in a buildspec file.
- **Secure IAM Roles**: Ensure IAM roles have the least privilege required.
- **Monitor Builds**: Use CloudWatch Metrics and Logs to monitor build performance and troubleshoot issues.
- **Optimize Compute Types**: Select appropriate compute types to balance performance and cost.
- **Cache Dependencies**: Use caching to speed up build times and reduce costs.
- **VPC Integration**: Run builds in a VPC for additional security and access to private resources.

