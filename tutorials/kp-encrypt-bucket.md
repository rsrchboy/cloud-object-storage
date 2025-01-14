---

copyright:
   years: 2022
lastupdated: "2022-04-07"

keywords: tutorials

subcollection: service-name # <To find this value, look up the subcollection value in that service's `toc.yaml` file and use the exact value (case matters). Do not add your own subcollection value, and do not set any platform subcollection values.>

In the YAML definiton, add:
```yaml
content-type: tutorial
services: <subcollection names from toc> # Only if the tutorial includes multiple services. If it only uses your service, don't specify. DO NOT set any platform subcollections.
account-plan: lite # Set `lite` if tutorial can be completed by using only Lite plan services; Set `paid` if the tutorial requires a pay-go or subscription versions of plans for the service
completion-time: 10m # Estimated time to complete the steps in this tutorial. Minute values are supported up to 90 minutes. Whole hours are also supported; for example: 2h

---

{{site.data.keyword.attribute-definition-list}}

<!-- The title of your tutorial should be in active voice and and start with a verb. If you include product names, makes sure to use the non-trademarked short version keyref. -->
<!-- Make sure each H1/H2/H3/etc. heading is _unique_ to your tutorial by adding a short but human-readable identifier. For example, instead of just "#overview", use "#cd-kube-overview" -->

# Set up to create a bucket and encrypt with Key Protect (KP)
{: #tutorial-kp-encrypt-bucket}
{: toc-content-type="tutorial"} <!-- Always use this value -->
{: toc-services="storage instances, Buckets"} <!-- Only if multi-service - use same values from services metadata above-->
{: toc-completion-time="10m"} <!-- Use same value from completion-time metadata above-->

<!-- The short description should be a single, concise paragraph that contains one or two sentences and no more than 50 words. Briefly mention what the user's learning goal is and include the following SEO keywords in the title short description: IBM Cloud, ServiceName, tutorial.-->

In this tutorial, you learn how to create a bucket and choose KP encrption.  The final step is verifying the setup works.
{: shortdesc}

<!-- It's recommended to include an architectural diagram that shows how the services that are used in this tutorial interact. SVG is the recommended format. If you include a diagram, include a brief text-based description of the workflow shown in the diagram, using active voice to describe the workflow. This makes the content more searchable and improves accessibility. -->

<!-- [Architectural diagram](images/image.svg)
{: figure caption="Figure 1. A diagram that shows the architecture for my tutorial."}

The pipeline that you create has the following architecture:
1. Create a bucket
1. Choose KP encryption
1. Verify that it works-->

## Before you begin
{: #kp-encrypt-bucket-prereqs}

<!-- List any access, setup, or knowledge that the user must have before they start the tutorial. Be sure to link to any related documentation or resources to help the user complete these prerequisites.-->

<!-- Note: Currently no format for checkboxes. Let's check with design if required for first pass -->

{: #kp-begin}

Before you plan on using Key Protect with Cloud Object Storage buckets, you need:

- An [IBM Cloud™ Platform account](http://cloud.ibm.com/)
- An [instance of IBM Cloud Object Storage](http://cloud.ibm.com/catalog/services/cloud-object-storage)

You will also need to ensure that a service instance is created by using the [IBM Cloud catalog](https://cloud.ibm.com/catalog) and appropriate permissions are granted. This tutorial does not outline the step-by-step instructions to help you get started.  This information is found in section  [Server-Side Encryption with IBM Key Protect (SSE-KP)](https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-kp)

<!-- For each step in your tutorial, add an H2 section. The title should be task-oriented and descriptive. If you find your tutorial going over 9 steps, consider whether your substeps can be grouped differently or whether your tutorial should be a multi-part series. -->

## Create a bucket
{: #kp-encrypt-bucket-create}
{: step}

When your key exists in Key Protect and you authorize a service for use with IBM COS, associate the key with a new bucket:

1. Navigate to your instance of Object Storage.
1. Click **Create bucket**.
1. Select **Custom bucket**.
1. Enter a bucket name, select the **Regional** resiliency, and choose a location and storage class.

You can choose to use Key Protect to manage encryption for a bucket only at the time of creation. It isn't possible to change an existing bucket to use Key Protect.
{: important}

## Choose KP encryption
{: #kp-encrypt-bucket-select}
{: step}

1. Scroll down to **Service integrations (optional)**, toggle **Key management disabled** to enable encryption key management and click on **Use existing instance**.
1. Select the associated service instance and key, and click **Associate key**.
1. Verify the information is correct.
1. Click **Create bucket**.

If bucket creation fails with a `400 Bad Request` error with the message `The Key CRN could not be found`, ensure that the CRN is correct and that the service to service authorization policy exists.
{: tip}

In the **Buckets** listing, the bucket has a _View_ link under **Attributes** where you can verify that the bucket has a Key Protect key enabled.

## Verify that it works
{: #kp-encrypt-bucket-verify}
{: step}

1. In the **Buckets** listing, the bucket has **Advanced Configurations** where you can click the tab to verify that the bucket has Key Protect enabled.
1. Scroll down to **Advanced configurations** and locate **Associated key management service** .
1. Verify the information is correct.

<!-- Introduce each major step with a description of what it will accomplish. If there are sequential substeps, use an ordered list for each substep. Don't include the step number. -->

<!-- For commands, introduce the command in a sentence first. Then surround what the user must enter in the command prompt with three backticks, and set the programming language if it applies. After the code block, add a {: pre} attribute to add a $ before the command and a copy link. -->


