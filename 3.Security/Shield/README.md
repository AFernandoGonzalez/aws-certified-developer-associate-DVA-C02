# AWS Shield Cheat Sheet

## Overview
AWS Shield is a managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS. It provides always-on detection and automatic inline mitigations that minimize application downtime and latency.

## Use Cases
- Protecting web applications from DDoS attacks
- Ensuring availability and performance during DDoS attacks
- Integrating with other AWS services for enhanced security

## Key Features
- **AWS Shield Standard**: Provides automatic protection against common, most frequently occurring network and transport layer DDoS attacks.
- **AWS Shield Advanced**: Provides additional detection and mitigation against larger and more sophisticated attacks, near real-time visibility into attacks, and integration with AWS WAF.
- **24/7 DDoS Response Team (DRT)**: Available with Shield Advanced to assist during DDoS attacks.
- **Cost Protection**: Financial protections to safeguard against scaling charges resulting from DDoS attacks on AWS resources.

## Key Concepts

### AWS Shield Standard
- **Automatic Protection**: Automatically included with AWS services at no additional cost.
- **Network Layer (Layer 3) Protection**: Protects against attacks like SYN/ACK floods, UDP reflection attacks.
- **Transport Layer (Layer 4) Protection**: Protects against attacks targeting TCP/UDP protocols.

### AWS Shield Advanced
- **Enhanced Protection**: Includes advanced DDoS protection and detection.
- **Web Application Layer (Layer 7) Protection**: Protects against more sophisticated attacks targeting application layer.
- **Advanced Attack Mitigations**: Real-time attack visibility and detailed attack diagnostics.
- **DDoS Response Team (DRT)**: Access to AWS DRT for assistance during attacks.
- **Cost Protection**: Provides financial safeguards against unexpected costs due to DDoS attacks.
- **Integration with AWS WAF**: Combines with AWS WAF for comprehensive application layer protection.

## Monitoring and Metrics
- **CloudWatch Metrics**: Monitor DDoS attacks and mitigation activities.
- **AWS WAF Logs**: Gain visibility into web application layer attacks when integrated with AWS WAF.
- **Shield Advanced Dashboard**: Provides detailed visibility into DDoS attacks and their mitigation.

## Pricing
- **AWS Shield Standard**: Included at no additional cost with AWS services.
- **AWS Shield Advanced**: Monthly fee and usage-based data transfer fees.

## Key Terms
- **DDoS (Distributed Denial of Service)**: A type of attack that aims to make an online service unavailable by overwhelming it with traffic from multiple sources.
- **DRT (DDoS Response Team)**: AWS team available to assist customers with Shield Advanced during DDoS attacks.
- **Mitigation**: Actions taken to reduce the severity or impact of a DDoS attack.

## Best Practices
- **Enable Shield Advanced**: For critical applications that require enhanced DDoS protection.
- **Integrate with AWS WAF**: Use AWS WAF with Shield Advanced for comprehensive protection.
- **Monitor Metrics**: Use CloudWatch metrics and Shield Advanced dashboard for visibility.
- **Use Cost Protection**: Leverage Shield Advanced’s cost protection to safeguard against unexpected charges.

## Example: Enabling AWS Shield Advanced

### Step 1: Enable Shield Advanced
1. Sign in to the AWS Management Console.
2. Navigate to the AWS Shield console.
3. Choose "Enable AWS Shield Advanced."
4. Select the resources you want to protect (e.g., CloudFront distributions, Route 53 hosted zones, Elastic Load Balancers).
5. Review and confirm the settings.

### Step 2: Integrate with AWS WAF (Optional)
1. In the AWS WAF console, create a new WebACL.
2. Add rules to the WebACL to filter malicious traffic.
3. Associate the WebACL with the resources protected by Shield Advanced.

