---
title: Rules
layout:  null
tab: true
order: 1
tags: kscanner
---
# Kubernetes Security and Compliance Rules

### K001: ServiceAccount token mounting
Pod having ServiceAccount token mounted, when get compromised can 
lead to privilege escalation. *automountServiceAccountToken* need to be set explicitly to false.
* Severity: Medium
* Rule:  <pre><code>Pod=~(Spec.automountServiceAccountToken.exists()) | (
                    Spec.automountServiceAccountToken == True)</code></pre>
* Remediation: Set automountServiceAccountToken to false for ServiceAccount and Workloads. 
* Tags: `CIS-5.1.6`  `checker` 

