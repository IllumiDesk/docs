---
description: Install IllumiDesk with the Canvas LMS using LTI v1.1
---

# Canvas LMS with LTI 1.1

### Overview

LTI v1.1 uses credentials consistent with the `OAuth1` standard. The Canvas LMS requires tool providers to provide users with a `consumer key`, `shared secret`, and `configuration URL`. For testing, IllumiDesk offers generic test credentials. For dedicated testing or production environments, IllumiDesk delivers unique credentials and configuration URLs for each Canvas LMS instance.

### Test Environment

Regardless of whether you install IllumIDesk using Canvas's App Center or as an External App, the following key, secret, and configuration URL will authenticate your Canvas LMS instance with IllumiDesk's shared test environment:

* **Consumer Key**: `ild_test_consumer_key`
* **Shared Secret**: `ild_test_shared_secret`
* **Configuration URL:** [https://configs.illumidesk.com/lti/11/my.xml](https://configs.illumidesk.com/lti/11/my.xml)

{% hint style="info" %}
It's possible that you may encounter intermittent connections during heavy loads with the multi-tenant test environment. If you would like to test the application with dedicated resources, reach out to us [via our contact form so we can process your request](https://www.illumidesk.com/getstarted).
{% endhint %}

#### Option 1 - Install IllumiDesk as an External Application

1. If you need to manually install the IllumiDesk application, navigate to Course --&gt; Settings --&gt; Apps --&gt; +App.
2. Select the `Configuration URL` as the `Configuration Type`
3. Enter the provided `Consumer Key`, `Shared Secret` and `Config URL` into the form
4. Click Submit to save your settings

![](../.gitbook/assets/screen-shot-2020-04-27-at-9.27.48-am.png)

You may have access to Canvas's full list of available applications located within Canvas's **App Center**. It's more common, however, that your instance's configuration settings have permissions to install IllumiDesk as an **external application**. Have your LMS administrator refer to one of the options below to enable the IllumiDesk tool with your course.

#### Option 2 - Install IllumiDesk from the App Center

If you or your LMS administrator has access to the IllumiDesk App Center applications, then the configuration URL for the shared \(multi-tenant\) is already included by default.

1. To install IllumiDesk from the App Center, navigate to Course --&gt; Settings --&gt; Apps --&gt; View App Center.
2. Type `illumidesk` in the search text field
3. Click on the IllumiDesk application icon
4. Click on the + Add App button
5. Enter the consumer key and shared secret in the available modal
6. Confirm by clicking on Add App

![](../.gitbook/assets/screen-shot-2020-04-27-at-10.16.56-am.png)

### Dedicated or Production Environments

The same steps above apply if you would rather install IllumiDesk with dedicated resources. The only variables that change are the consumer key / shared secret pair and the configuration URL will reflect the configuration settings required to access these dedicated resources.

