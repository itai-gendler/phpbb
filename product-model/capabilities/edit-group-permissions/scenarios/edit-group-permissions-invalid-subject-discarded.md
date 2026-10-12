---
{
  "kind": "validation",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits proposed global recipient collection assignment changes.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::group-permissions"
        }
      }
    },
    {
      "text": "Submitted subject identifiers include missing subjects.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::group-permissions"
        }
      }
    },
    {
      "text": "Invalid subjects are discarded; remaining valid subjects can receive the accepted selected settings.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "group-permissions",
          "effect": "changes",
          "facts": [
            "Settings",
            "Permission role"
          ]
        }
      ],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::group-permissions"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_permissions.php#set_permissions"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/auth.php#acl_set"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/auth.php#acl_delete"
    }
  ]
}
---

# Edit group permissions — invalid subject discarded

## Trigger

Submitted subject identifiers include missing subjects.

## Outcome

Invalid subjects are discarded; remaining valid subjects can receive the accepted selected settings.
