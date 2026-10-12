---
{
  "kind": "validation",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator requests an registered identity's effective global mask.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-masks"
        }
      }
    },
    {
      "text": "The requested mask/trace reaches its authority-refusal branch.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-masks"
        }
      }
    },
    {
      "text": "Permission decisions and trace are not disclosed.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::permission-masks"
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

# View permissions — authority refused

## Trigger

The requested mask/trace reaches its authority-refusal branch.

## Outcome

Permission decisions and trace are not disclosed.
