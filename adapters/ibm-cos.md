# IBM Cloud Object Storage CloudEvents Adapter

This document describes how to convert
[IBM Cloud Object Storage events](https://cloud.ibm.com/docs/services/cloud-object-storage?topic=cloud-object-storage-at-events)
into CloudEvents.

IBM COS event documentation:
https://cloud.ibm.com/docs/services/cloud-object-storage?topic=cloud-object-storage-at-events

All COS events are converted into CloudEvents using the
same pattern as described in the following table:

| CloudEvents Attribute | Value                                           |
| :-------------------- | :---------------------------------------------- |
| `id`                  | "requestData.requestId" |
| `source`              | "target.id" value         |
| `specversion`         | `1.0-rc1`                                       |
| `type`                | `com.ibm.` + "action" value         |
| `datacontenttype`     | COS event type (e.g. `application/json`)         |
| `dataschema`          | Omit                                            |
| `subject`             | "target.name" value                           |
| `time`                | "eventTime" value                               |
| `data`                | COS event                                        |



