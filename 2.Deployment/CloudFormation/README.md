# AWS CloudFormation Cheat Sheet

## Overview
AWS CloudFormation is a service that helps you model and set up your Amazon Web Services resources so that you can spend less time managing those resources and more time focusing on your applications.

## Use Cases
- Automate resource provisioning and configuration
- Simplify infrastructure management
- Implement Infrastructure as Code (IaC)
- Maintain consistent environment setups

## Key Features
- **Stacks**: Collections of AWS resources that you can manage as a single unit.
- **Templates**: JSON or YAML formatted text files that describe the AWS resources required for your application.
- **Change Sets**: Previews of how proposed changes to a stack might impact your running resources.
- **Drift Detection**: Identifies stack resources that have been changed outside of CloudFormation management.
- **StackSets**: Manage stacks across multiple accounts and regions.

## Key Concepts

### Templates
- **Structure**: Contains Resources, Parameters, Mappings, Conditions, Outputs, and Metadata sections.
- **Resources**: AWS resources that you want to create and configure.
- **Parameters**: Input values that can be supplied at stack creation.
- **Mappings**: Static mappings like region to AMI ID.
- **Conditions**: Define conditions to control resource creation.
- **Outputs**: Values that you can import into other stacks.

### Stacks
- **Stack**: A collection of AWS resources you can manage as a single unit.
- **Nested Stacks**: Stacks created as part of other stacks.
- **Stack Policies**: Controls updates to stack resources.

### Change Sets
- **Change Set**: Summary of proposed changes to a stack.
- **Execute Change Set**: Apply the changes described in a Change Set.

### Drift Detection
- **Drift**: A resource configuration that has been changed outside of CloudFormation management.
- **Drift Detection**: Identifies and reports drift on stack resources.

## Security
- **IAM Roles**: CloudFormation can assume IAM roles to create and manage resources.
- **Stack Policies**: JSON policies to protect critical stack resources from updates.

## Monitoring and Metrics
- **CloudWatch Alarms**: Monitor stack creation and update events.
- **CloudFormation Events**: Track stack creation, updates, and deletion activities.

## Pricing
- CloudFormation is free to use. You only pay for the AWS resources created.

## Common Commands
| Command                                         | Description                                     |
|-------------------------------------------------|-------------------------------------------------|
| `aws cloudformation create-stack`               | Create a new CloudFormation stack               |
| `aws cloudformation update-stack`               | Update an existing CloudFormation stack         |
| `aws cloudformation delete-stack`               | Delete a CloudFormation stack                   |
| `aws cloudformation describe-stacks`            | Describe one or more CloudFormation stacks      |
| `aws cloudformation list-stacks`                | List all CloudFormation stacks                  |
| `aws cloudformation validate-template`          | Validate a CloudFormation template              |
| `aws cloudformation create-change-set`          | Create a change set for an existing stack       |
| `aws cloudformation execute-change-set`         | Execute a change set                            |
| `aws cloudformation describe-change-set`        | Describe a change set                           |
| `aws cloudformation detect-stack-drift`         | Detect drift on a stack                         |
| `aws cloudformation describe-stack-drift-detection-status` | Describe the status of a drift detection operation |

## Key Terms
- **Template**: JSON or YAML file that describes AWS resources.
- **Stack**: Collection of AWS resources you can manage as a single unit.
- **Change Set**: Summary of proposed changes to a stack.
- **Drift**: Resource configuration changes outside of CloudFormation.

## Best Practices
- **Use Parameters**: Allow customization of stack creation.
- **Validate Templates**: Always validate your templates before deploying.
- **Use Nested Stacks**: Modularize and reuse templates.
- **Implement Stack Policies**: Protect critical resources from accidental updates.
- **Monitor Changes**: Use Change Sets and Drift Detection.

## Example: Creating a Stack
```bash
aws cloudformation create-stack \
    --stack-name my-stack \
    --template-body file://template.yaml \
    --parameters ParameterKey=InstanceType,ParameterValue=t2.micro
