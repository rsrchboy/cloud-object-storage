---

copyright:
  years: 2021
lastupdated: "2021-12-01"

keywords:  object storage, satellite, local

subcollection: cloud-object-storage


---
{:new_window: target="_blank"}
{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:download: .download} 
{:table: .aria-labeledby="caption"}
{:faq: data-hd-content-type='faq'}
{:support: data-reuse='support'}

# Supported APIs
{: #apis-cos-satellite}

{{site.data.keyword.cos_short}} for {{site.data.keyword.satelliteshort}} supports most S3 APIs.
{: shortdesc}

## Supported S3 APIs
{: #apis-satellite-supported}

* `AbortMultipartUpload`
* `CompleteMultipartUpload`
* `CopyObject`
* `CreateBucket`
* `CreateMultipartUpload`
* `DeleteBucket`
* `DeleteBucketCors`
* `DeleteBucketLifecycle`
* `DeleteBucketWebsite`
* `DeleteObject`
* `DeleteObjects`
* `DeleteObjectTagging`
* `DeletePublicAccessBlock`
* `GetBucketAcl`
* `GetBucketCors`
* `GetBucketLifecycle`
* `GetBucketLocation`
* `GetBucketVersioning`
* `GetBucketWebsite`
* `GetObject`
* `GetObjectAcl`
* `GetObjectTagging`
* `GetPublicAccessBlock`
* `HeadBucket`
* `HeadObject`
* `ListBuckets`
* `ListMultipartUploads`
* `ListObjects`
* `ListObjectsV2`
* `ListObjectVersions`
* `ListParts`
* `PutBucketAcl`
* `PutBucketCors`
* `PutBucketLifecycle` (expiration rules only)
* `PutBucketVersioning`
* `PutBucketWebsite`
* `PutObject`
* `PutObjectAcl`
* `PutObjectTagging`
* `PutPublicAccessBlock`
* `UploadPart`
* `UploadPartCopy`

## Unsupported S3 APIs
{: #apis-satellite-unsupported}

* `PutBucketLifecycle` (archive rules only)
* `RestoreObject`