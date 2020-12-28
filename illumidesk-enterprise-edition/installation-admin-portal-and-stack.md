---
description: >-
  Review this article to get information on how to install the Admin Portal. The
  recommended installation option will depend on how your environment is set up.
---

# Initial Installation

## Release Channels

Regardless of the installation type \(existing clusters or stand-alone \(embedded\) clusters\) the installation is managed via the concept of “**Channels**”. Channels typically are associated with **Alpha, Beta, and Stable** channels but are sometimes associated with the customer’s environments, such as **UAT, OAT, and Production**. The example installation scripts below are for the default ****channels \(Alpha, Beta, Stable\). If you are using another channel, then simply replace the `-<channel-name>` part with the channel associated to your application's environment.

## **Existing Cluster Installation**

If you have **an existing cluster** you can run the following command from a workstation that has `kubectl` access to the cluster. Existing clusters refer to managed services, such as **AWS EKS, AKS,** or **GKE**.

Like the embedded cluster option, the installation script should specify the release channel for the application. The **Alpha**, **Beta**, and **Stable** channels are the default channel names, but you can use other channel names \(or add more\) as desired.

The first step is to install the required dependencies. Use the command below to install the `kots` CLI tool in your local environment:

```text
curl https://kots.io/install | bash
```

{% hint style="info" %}
The **IllumiDesk Enterprise Edition \(EE\)** relies on the **`kots`** CLI to install and configure the Admin portal. The **`kots`** CLI is a **`kubectl`** plug-in. You will therefore need access to **`kubectl`**to use **`kots`.**You will also need to ensure that **`kubectl`**is set to the right context so that the Admin portal is installed in the correct Kubernetes context \(cluster and namespace\).
{% endhint %}

The next step is to install the application itself. Use the command below to install the IllumiDesk Enterprise Edition application:

```text
kubectl kots install illumidesk-enterprise/beta
```

Once the script executes it will execute a series of tasks to complete the Admin portal installation and the IllumIDesk Enterprise Edition's initial installation. For reference, these steps are described below:

* Installs the Admin Console on the cluster and sets up a port forward on the [ClusterIP ](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types)to enable you to access the Admin portal from [https://localhost:8800](https://localhost:8800).
* Runs a series of predefined preflight checks to ensure the environment meets all resource and application requirements.
* Installs the application itself within the cluster into a dedicated namespace.
* Prompts the user to confirm a password to access the Admin Console.

Once you have completed this step then you can proceed to configure a[ TLS certification for the Admin Console](enable-a-tls-certificate-for-your-admin-console.md).

## Embedded Kubernetes Installation

The installation is managed via the concept of “**Channels**”. Channels typically are associated with **Alpha, Beta, and Stable** channels but are sometimes associated with the customer’s environments, such as **UAT, OAT, and Production**. The example installation scripts below are for the default ****channels \(Alpha, Beta, Stable\). If you are using another channel, then simply replace the `-<channel-name>` part with the channel associated with your application's environment.

{% hint style="info" %}
For stable channels, the &lt;**-channel-name&gt;** portion is removed altogether.
{% endhint %}

To set up your cluster with the **alpha channel**, run the following script below:

```text
curl -sSL https://k8s.kurl.sh/illumidesk-enterprise-alpha| sudo bash
```

The **beta channel** would simply replace the `-alpha` portion with `-beta`:

```text
curl -sSL https://k8s.kurl.sh/illumidesk-enterprise-beta | sudo bash
```

Production environments would not specify the channel at all, so the script should look like so:

```text
curl -sSL https://k8s.kurl.sh/illumidesk-enterprise | sudo bash
```

After about 10 minutes, you should be able to follow the on-screen instructions to port **http://&lt;ip&gt;:8800** on your server to configure your instance, add additional nodes, check for updates, among other tasks.

{% hint style="info" %}
The **&lt;ip&gt;** mentioned above refers to the instance's external IP address. For example, if the instance where the application is installed is `192.168.1.10` then you would access the Admin Console with the  `http://192.168.1.10:8800` address.
{% endhint %}

{% hint style="warning" %}
Sometimes the Admin Portal will not load with the first attempt due to timeout issues due to internal security rules. In these cases, it may help run the installation command above and try again.
{% endhint %}

Once you have completed installing the cluster with the embedded \(stand-alone\) option, then you can proceed to configure a[ TLS certification for the Admin Console](enable-a-tls-certificate-for-your-admin-console.md).

