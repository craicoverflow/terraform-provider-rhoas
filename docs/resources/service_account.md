---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "rhoas_service_account Resource - terraform-provider-rhoas"
subcategory: ""
description: |-
  rhoas_service_account manages a service account in Red Hat OpenShift Streams for Apache Kafka.
---

# rhoas_service_account (Resource)

`rhoas_service_account` manages a service account in Red Hat OpenShift Streams for Apache Kafka.

## Example Usage

```terraform
terraform {
  required_providers {
    rhoas = {
      source  = "pmuir/rhoas"
    }
  }
}

provider "rhoas" {}

resource "rhoas_service_account" "foo" {
  service_account {
    name = "foo"
    description = "blah blah blah"
  }
}

output "client_id" {
  value = rhoas_service_account.foo.service_account[0].client_id
}

output "client_secret" {
  value = rhoas_service_account.foo.service_account[0].client_secret
  sensitive = true
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **service_account** (Block List, Min: 1, Max: 1) (see [below for nested schema](#nestedblock--service_account))

### Optional

- **id** (String) The ID of this resource.
- **timeouts** (Block, Optional) (see [below for nested schema](#nestedblock--timeouts))

<a id="nestedblock--service_account"></a>
### Nested Schema for `service_account`

Required:

- **name** (String) The name of the service account

Optional:

- **description** (String) A description of the service account

Read-Only:

- **client_id** (String) The client id associated with the service account
- **client_secret** (String) The client secret associated with the service account. It must be stored by the client as the server will not return it after creation
- **owner** (String) The username of the Red Hat account that owns the service account


<a id="nestedblock--timeouts"></a>
### Nested Schema for `timeouts`

Optional:

- **create** (String)

