---
description: Install IllumiDesk with your LMS using the LTI v1.3 standard
---

# Learning Tools Interoperability \(LTI\) 1.3

## Overview

The Learning Tools Interoperability \(LTI\) v1.3 standard the the latest LTI standard published by [IMS Global](https://www.imsglobal.org/). As mentioned in the [LTI overview section](../../general-topics/learning-tools-interoperability-lti.md#learning-tools-interoperability-lti-overview), IllumiDesk is an active member of IMS Global and maintains the [IMS Global interoperability](https://site.imsglobal.org/certifications/illumidesk-llc/illumidesk#cert_pane_nid_186771) certification.

{% page-ref page="../../general-topics/learning-tools-interoperability-lti.md" %}

## Test Environment

Fortunately the LTI v1.3 makes it a breeze to install IllumiDesk as an external tool with your Canvas instance. We offer a multi-tenant test environment that allows you to get up and running in no time! The LTI v1.3 standard requires consumers to integrate with providers using configuration files structured as JSON which should also contain a public key published with the JSON Web Key standard.

The following URL provides the configuration settings along with the JWK required by your LTI compliant LMS:

```text
https://my.illumidesk.com/hub/jwks
```

{% hint style="info" %}
It's possible that you may encounter intermittent connections during heavy loads with the multi-tenant test environment. If you would like to test the application with dedicated resources, reach out to us [via our contact form so we can process your request](https://www.illumidesk.com/getstarted).
{% endhint %}

## Dedicated and/or Production Environments

The same steps above apply if you would rather install IllumiDesk with dedicated resources. The only variables that change are the consumer key / shared secret pair and the configuration URL will reflect the configuration settings required to access these dedicated resources.



