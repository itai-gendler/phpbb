---
{
  "kind": "edge",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits a supplied selected role definition and class settings.",
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
      "text": "Header validation succeeds but no setting survives class filtering.",
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
      "text": "Name/Description and selected-class header are written before WRONG_PERMISSION_SETTING_FORMAT; the submitted settings are not replaced.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "permission-role",
          "effect": "changes",
          "facts": [
            "Name",
            "Description",
            "Permission class"
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

# Edit permission role — changed before settings refusal

## Trigger

Header validation succeeds but no setting survives class filtering.

## Outcome

Name/Description and selected-class header are written before WRONG_PERMISSION_SETTING_FORMAT; the submitted settings are not replaced.
