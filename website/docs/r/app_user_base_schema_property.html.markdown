---
layout: 'okta'
page_title: 'Okta: okta_app_user_base_schema_property'
sidebar_current: 'docs-okta-resource-app-user-base-schema-property'
description: |-
  Manages an Application User Base Schema property.
---

# okta_app_user_base_schema_property

Manages an Application User Base Schema property.

This resource allows you to configure a base app user schema property.

## Example Usage

```hcl
resource "okta_app_user_base_schema_property" "example" {
  app_id      = "<app id>"
  index       = "customPropertyName"
  title       = "customPropertyName"
  type        = "string"
  master      = "OKTA"
}
```

## Argument Reference

The following arguments are supported:

- `app_id` - (Required) The Application's ID the user schema property should be assigned to.

- `index` - (Required) The property name.

- `title` - (Required) The property display name.

- `type` - (Required) The type of the schema property. It can be `"string"`, `"boolean"`, `"number"`, `"integer"`, `"array"`, or `"object"`.

- `required` - (Optional) Whether the property is required for this application's users.

- `permissions` - (Optional) Access control permissions for the property. It can be set to `"READ_WRITE"`, `"READ_ONLY"`, `"HIDE"`.

- `master` - (Optional) Master priority for the user schema property. It can be set to `"PROFILE_MASTER"` or `"OKTA"`.

- `pattern` - (Optional) The validation pattern to use for the subschema, only available for `login` property. Must be in form of `.+`, or `[<pattern>]+`.

## Attributes Reference

- `app_id` - ID of the application the user property is associated with.

- `index` - ID of the user schema property.

## Import

App user base schema property can be imported via the property index and app id.

```
$ terraform import okta_app_user_base_schema_property.example &#60;app id&#62;/&#60;property name&#62;
```
