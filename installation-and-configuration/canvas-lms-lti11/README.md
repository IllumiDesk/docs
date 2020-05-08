---
description: Install IllumiDesk with your LMS using the LTI v1.1 standard
---

# Learning Tools Interoperability \(LTI\) 1.1

## Overview

LTI v1.1 uses credentials consistent with the `OAuth1` standard. The Canvas LMS requires tool providers to provide users with a `consumer key`, `shared secret`, and `configuration URL`. For testing, IllumiDesk offers generic test credentials. For dedicated testing or production environments, IllumiDesk delivers unique credentials and configuration URLs for each Canvas LMS instance.

## Test Environment

Regardless of whether you install IllumIDesk using Canvas's App Center or as an External App, the following key, secret, and configuration URL will authenticate your Canvas LMS instance with IllumiDesk's shared test environment:

* **Consumer Key**: `ild_test_consumer_key`
* **Shared Secret**: `ild_test_shared_secret`
* **Configuration URL:** [https://configs.illumidesk.com/lti/11/my.xml](https://configs.illumidesk.com/lti/11/my.xml)

{% hint style="info" %}
It's possible that you may encounter intermittent connections during heavy loads with the multi-tenant test environment. If you would like to test the application with dedicated resources, reach out to us [via our contact form so we can process your request](https://www.illumidesk.com/getstarted).
{% endhint %}

## Dedicated and/or Production Environments

The same steps above apply if you would rather install IllumiDesk with dedicated resources. The only variables that change are the consumer key / shared secret pair and the configuration URL will reflect the configuration settings required to access these dedicated resources.

