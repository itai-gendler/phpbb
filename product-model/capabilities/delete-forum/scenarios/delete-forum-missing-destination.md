---
{
  "kind": "validation",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator confirms supplied delete-content/subforum choices.",
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
      "text": "A required content/subforum destination is absent or invalid.",
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
      "text": "The deletion error is displayed and the requested deletion/movement is not completed.",
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

# Delete forum — missing destination

## Trigger

A required content/subforum destination is absent or invalid.

## Outcome

The deletion error is displayed and the requested deletion/movement is not completed.
