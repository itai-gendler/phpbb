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
      "text": "The name is empty/duplicate in class, description too long or form invalid.",
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
      "text": "The definition error is displayed before successful role creation.",
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

# Create permission role — invalid or duplicate name

## Trigger

The name is empty/duplicate in class, description too long or form invalid.

## Outcome

The definition error is displayed before successful role creation.
