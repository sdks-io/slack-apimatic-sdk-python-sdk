
# Team Object

*This model accepts additional fields of type Any.*

## Structure

`TeamObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `archived` | `bool` | Optional | - |
| `avatar_base_url` | `str` | Optional | - |
| `created` | `int` | Optional | - |
| `date_create` | `int` | Optional | - |
| `deleted` | `bool` | Optional | - |
| `description` | `str` | Optional | - |
| `discoverable` | `Any` | Optional | - |
| `domain` | `str` | Required | - |
| `email_domain` | `str` | Required | - |
| `enterprise_id` | `str` | Optional | **Constraints**: *Pattern*: `^[E][A-Z0-9]{8,}$` |
| `enterprise_name` | `str` | Optional | - |
| `external_org_migrations` | [`ExternalOrgMigrations`](../../doc/models/external-org-migrations.md) | Optional | - |
| `has_compliance_export` | `bool` | Optional | - |
| `icon` | [`ObjsIcon`](../../doc/models/objs-icon.md) | Required | - |
| `id` | `str` | Required | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `is_assigned` | `bool` | Optional | - |
| `is_enterprise` | `int` | Optional | - |
| `is_over_storage_limit` | `bool` | Optional | - |
| `limit_ts` | `int` | Optional | - |
| `locale` | `str` | Optional | - |
| `messages_count` | `int` | Optional | - |
| `msg_edit_window_mins` | `int` | Optional | - |
| `name` | `str` | Required | - |
| `over_integrations_limit` | `bool` | Optional | - |
| `over_storage_limit` | `bool` | Optional | - |
| `pay_prod_cur` | `str` | Optional | - |
| `plan` | [`Plan`](../../doc/models/plan.md) | Optional | - |
| `primary_owner` | [`ObjsPrimaryOwner`](../../doc/models/objs-primary-owner.md) | Optional | - |
| `sso_provider` | [`SsoProvider`](../../doc/models/sso-provider.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "archived": false,
  "avatar_base_url": "avatar_base_url4",
  "created": 18,
  "date_create": 124,
  "deleted": false,
  "domain": "domain0",
  "email_domain": "email_domain4",
  "icon": {
    "image_102": "image_1020",
    "image_132": "image_1326",
    "image_230": "image_2308",
    "image_34": "image_340",
    "image_44": "image_440",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "id": "id4",
  "name": "name4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

