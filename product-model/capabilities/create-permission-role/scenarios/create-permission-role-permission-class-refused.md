---
{
  "kind": "validation",
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
      "text": "The selected creation request reaches its class-refusal branch.",
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
      "text": "No role is created.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
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

# Create permission role — permission class refused

## Trigger

The selected creation request reaches its class-refusal branch.

## Outcome

No role is created.
