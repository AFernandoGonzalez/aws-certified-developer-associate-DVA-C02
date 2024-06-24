# AWS Cognito Cheat Sheet

## Overview
AWS Cognito provides authentication, authorization, and user management for web and mobile applications. It allows users to sign in through social identity providers or enterprise identity providers via SAML 2.0 and provides access control for AWS resources.

## Use Cases
- User authentication for web and mobile apps
- Identity federation with social and enterprise providers
- Secure access to AWS resources
- User data synchronization across devices

## Key Features
- **User Pools**: Manage user registration, authentication, and account recovery.
- **Identity Pools**: Obtain temporary AWS credentials to access AWS services.
- **Federated Identities**: Integrate with social identity providers (e.g., Facebook, Google) and enterprise identity providers (SAML).
- **Multi-Factor Authentication (MFA)**: Enhance security with MFA.
- **User Profiles**: Store user attributes and preferences.
- **Lambda Triggers**: Customize workflows with AWS Lambda.

## Key Concepts

### User Pools
- **User Pools**: User directories that handle sign-up and sign-in functionality.
- **User Attributes**: Store information about users (e.g., name, email).
- **Groups**: Organize users and apply permissions.
- **App Clients**: Applications that interact with the user pool.
- **Multi-Factor Authentication (MFA)**: Add an extra layer of security.

### Identity Pools
- **Identity Pools**: Provide temporary AWS credentials for accessing AWS services.
- **Federated Identities**: Link user identities from different identity providers.
- **Roles**: Define permissions for authenticated and unauthenticated users.

### Authentication
- **Sign-Up**: Register new users.
- **Sign-In**: Authenticate users.
- **Password Recovery**: Enable users to reset their passwords.
- **Account Confirmation**: Verify user email or phone number.

### Federated Identities
- **Social Providers**: Integrate with Facebook, Google, Amazon, etc.
- **SAML Providers**: Integrate with enterprise identity providers using SAML 2.0.
- **OIDC Providers**: Integrate with OpenID Connect providers.

### Security
- **Multi-Factor Authentication (MFA)**: Use SMS or TOTP for MFA.
- **Password Policies**: Enforce password complexity and rotation policies.
- **Secure Tokens**: Use JWT for secure authentication tokens.
- **Encryption**: Encrypt data at rest and in transit.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor sign-in attempts, successful authentications, and other metrics.
- **CloudWatch Logs**: Log user authentication and sign-up events for monitoring and troubleshooting.
- **Cognito Events**: Trigger AWS Lambda functions based on events in Cognito.

## Pricing
- Based on the number of active users and the features used (e.g., MFA, federation).

## Key Terms
- **User Pool**: A directory for managing user registration and authentication.
- **Identity Pool**: A directory for providing temporary AWS credentials.
- **Federated Identity**: Linking user identities from various identity providers.
- **App Client**: An application that interacts with the user pool.
- **MFA**: Multi-Factor Authentication for enhanced security.
- **JWT**: JSON Web Token used for secure authentication tokens.

## Best Practices
- **Enable MFA**: Add an extra layer of security for user authentication.
- **Use Secure Password Policies**: Enforce strong password policies.
- **Leverage Lambda Triggers**: Customize authentication workflows with AWS Lambda.
- **Monitor Metrics and Logs**: Use CloudWatch to monitor and troubleshoot authentication events.
- **Integrate with Identity Providers**: Use federated identities to streamline user access.
- **Secure User Data**: Encrypt sensitive user data at rest and in transit.

