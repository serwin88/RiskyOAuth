# README - Curated List of Discovered Malicious M365 OAuth Apps

## Overview

This repository contains a curated list of known malicious Microsoft 365 (M365) OAuth applications. These applications have been identified as potentially harmful or malicious based on their behavior, scope of permissions requested, and the activity associated with their use. The purpose of this repository is to help security professionals, administrators, and threat analysts quickly identify and mitigate risks associated with malicious OAuth apps within their Microsoft 365 environments.

OAuth applications in Microsoft 365 (formerly Office 365) are used to enable third-party integrations with Microsoft services. While legitimate apps provide useful functionalities, malicious or compromised apps can be exploited to gain unauthorized access to sensitive data, execute harmful actions, and compromise security.

This list is continually updated to reflect new findings and can be used for detecting and mitigating security risks related to OAuth applications within Microsoft 365.

## Table of Contents

1. [Purpose](#purpose)
2. [How to Use](#how-to-use)
3. [Contributing](#contributing)
4. [Application Data Format](#application-data-format)
5. [Malicious Application Examples](#malicious-application-examples)
6. [How to Report Malicious Apps](#how-to-report-malicious-apps)
7. [References](#references)
8. [Disclaimer](#disclaimer)

## Purpose

The primary objective of this repository is to:

- Provide a reliable and regularly updated list of known malicious OAuth applications used within Microsoft 365 environments.
- Help organizations identify potentially harmful apps that have been granted OAuth tokens, which could be used for unauthorized access.
- Assist in the mitigation and prevention of security threats associated with these apps.
- Serve as a valuable resource for threat detection tools, automated monitoring systems, and security audits.

## How to Use

Security teams and Microsoft 365 administrators can use this repository in various ways:

1. **Manual App Review**:
   - Review the list of malicious OAuth apps in this repository against the list of apps installed within your organization's Microsoft 365 environment.
   - Identify and remove any malicious applications or suspicious apps from your tenant.

2. **Automated Monitoring**:
   - Integrate this list with your organization's security tools to automatically flag any apps matching known malicious entries.
   - Use this list for automated periodic scans of newly registered apps in your Microsoft 365 environment.

3. **Incident Response**:
   - Leverage this list to identify compromised apps or apps exhibiting malicious behavior in case of an active security incident.

## Contributing

Contributions to this repository are welcome! If you identify new malicious OAuth apps or can provide more context on previously identified apps, feel free to submit an issue or a pull request. To contribute:

1. Fork the repository and clone it to your local environment.
2. Add the details of any new malicious OAuth apps following the structure outlined in the [Application Data Format](#application-data-format).
3. Submit a pull request with your changes.

Please ensure that any apps added are well-documented and include reliable sources or evidence supporting their classification as malicious.

## Application Data Format

Each malicious OAuth app entry should follow this data format for consistency and clarity:

```json
{
  "app_name": "Malicious OAuth App Name",
  "app_id": "00000000-0000-0000-0000-000000000000",
  "publisher": "Malicious App Publisher",
  "permissions": [
    "User.Read",
    "Mail.ReadWrite",
    "Directory.ReadWrite.All"
  ],
  "discovery_method": "Automated detection, reported by third-party researcher, etc.",
  "impact": "Data exfiltration, account compromise, etc.",
  "date_discovered": "2025-02-01",
  "reported_by": "Researcher Name or Organization",
  "references": [
    "https://malicious-app-report-link.com",
    "https://another-reliable-source.com"
  ]
}
```

- `app_name`: The name of the malicious OAuth app.
- `app_id`: Unique identifier for the OAuth app.
- `publisher`: The organization or developer responsible for the app.
- `permissions`: A list of permissions requested by the app (e.g., User.Read, Mail.ReadWrite).
- `discovery_method`: How the app was discovered, whether through automated detection or reported by researchers.
- `impact`: The potential consequences or impact of the malicious app (e.g., data exfiltration, account takeover).
- `date_discovered`: Date the app was first discovered or reported.
- `reported_by`: Name of the researcher or organization that reported the app.
- `references`: URLs or other references to reports, blog posts, or research documenting the app.

## Malicious Application Examples

Below are some examples of malicious OAuth apps that have been discovered in the wild:

### Example 1

```json
{
  "app_name": "Fake OAuth App",
  "app_id": "12345678-1234-1234-1234-1234567890ab",
  "publisher": "Fake Company Inc.",
  "permissions": [
    "User.Read",
    "Mail.Send",
    "Files.ReadWrite"
  ],
  "discovery_method": "Automated detection",
  "impact": "Data exfiltration, unauthorized email sending",
  "date_discovered": "2025-01-10",
  "reported_by": "Security Research Team",
  "references": [
    "https://example.com/malicious-app-details",
    "https://researcher-blog.com/fake-oauth-app-report"
  ]
}
```

### Example 2

```json
{
  "app_name": "Compromised OAuth App",
  "app_id": "abcd1234-abcd-1234-abcd-1234abcd5678",
  "publisher": "Compromised Developer",
  "permissions": [
    "Directory.ReadWrite.All",
    "Group.ReadWrite.All"
  ],
  "discovery_method": "Reported by third-party researcher",
  "impact": "Privilege escalation, group manipulation",
  "date_discovered": "2025-02-05",
  "reported_by": "External Security Analyst",
  "references": [
    "https://external-research.com/compromised-oauth-app"
  ]
}
```

## How to Report Malicious Apps

If you encounter a new malicious OAuth app that is not listed here, please report it by following these steps:

1. Verify that the app is indeed malicious by reviewing its permissions, behavior, and any potential indicators of compromise (IOC).
2. Gather details such as the app name, app ID, permissions, impact, and any relevant references.
3. Submit a new issue in this repository or create a pull request following the [Application Data Format](#application-data-format).

## References

- [Microsoft 365 Security and Compliance](https://www.microsoft.com/en-us/microsoft-365/security](https://learn.microsoft.com/en-us/microsoft-365/security/?view=o365-worldwide)
- [OAuth 2.0 Framework](https://tools.ietf.org/html/rfc6749)
- [Microsoft Identity Platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/)

## Disclaimer

This list is compiled based on information gathered from various security researchers, vendors, and organizations. While efforts are made to verify the details of each entry, we cannot guarantee the completeness or accuracy of the data provided. Always use additional methods of validation and risk assessment when managing OAuth apps within your organization.

