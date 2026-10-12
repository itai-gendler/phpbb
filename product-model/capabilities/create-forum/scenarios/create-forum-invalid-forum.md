---
{
  "kind": "validation",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits supplied posting area configuration without copied permissions.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::forum"
        }
      }
    },
    {
      "text": "Name/description/rules/password confirmation or destination/form validation fails.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::forum"
        }
      }
    },
    {
      "text": "The create process displays validation errors without creating the proposed container.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::forum"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php"
    }
  ]
}
---

# Create forum — invalid forum

## Trigger

Name/description/rules/password confirmation or destination/form validation fails.

## Outcome

The create process displays validation errors without creating the proposed container.
