---
{
  "kind": "edge",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits a unique name, bounded description, nonempty class settings and supplied form.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-role"
        }
      }
    },
    {
      "text": "Header validation succeeds but no submitted setting survives selected-class filtering.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-role"
        }
      }
    },
    {
      "text": "The role header/order is inserted before WRONG_PERMISSION_SETTING_FORMAT; the submitted settings are not stored and the header remains.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "permission-role",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Permission class",
            "Order"
          ]
        }
      ],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-role"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_permission_roles.php"
    }
  ]
}
---

# Create permission role — stored before settings refusal

## Trigger

Header validation succeeds but no submitted setting survives selected-class filtering.

## Outcome

The role header/order is inserted before WRONG_PERMISSION_SETTING_FORMAT; the submitted settings are not stored and the header remains.
