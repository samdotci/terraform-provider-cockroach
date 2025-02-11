---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "cockroach_cluster Resource - terraform-provider-cockroach"
subcategory: ""
description: |-
  Cluster Resource
---

# cockroach_cluster (Resource)

Cluster Resource



<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `cloud_provider` (String)
- `name` (String) Name of cluster
- `regions` (Attributes List) (see [below for nested schema](#nestedatt--regions))

### Optional

- `cockroach_version` (String)
- `dedicated` (Attributes) (see [below for nested schema](#nestedatt--dedicated))
- `serverless` (Attributes) (see [below for nested schema](#nestedatt--serverless))

### Read-Only

- `account_id` (String)
- `creator_id` (String)
- `id` (String) The ID of this resource.
- `operation_status` (String)
- `plan` (String)
- `state` (String)
- `upgrade_status` (String)

<a id="nestedatt--regions"></a>
### Nested Schema for `regions`

Required:

- `name` (String)

Optional:

- `node_count` (Number)
- `primary` (Boolean) Set to true to mark this region as the primary for a Serverless cluster. Exactly one region must be primary. Dedicated clusters expect to have no primary region.

Read-Only:

- `sql_dns` (String)
- `ui_dns` (String)


<a id="nestedatt--dedicated"></a>
### Nested Schema for `dedicated`

Optional:

- `disk_iops` (Number)
- `machine_type` (String)
- `num_virtual_cpus` (Number)
- `private_network_visibility` (Boolean) Set to true to assign private IP addresses to nodes. Required for CMEK and other advanced networking features.
- `storage_gib` (Number)

Read-Only:

- `memory_gib` (Number)


<a id="nestedatt--serverless"></a>
### Nested Schema for `serverless`

Optional:

- `spend_limit` (Number) Spend limit in US cents.
- `usage_limits` (Attributes) (see [below for nested schema](#nestedatt--serverless--usage_limits))

Read-Only:

- `routing_id` (String)

<a id="nestedatt--serverless--usage_limits"></a>
### Nested Schema for `serverless.usage_limits`

Required:

- `request_unit_limit` (Number) Maximum number of request units that the cluster can consume during the month.
- `storage_mib_limit` (Number) Maximum amount of storage (in MiB) that the cluster can have at any time during the month.


