---
{
  "kind": "validation",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits proposed configuration for a selected posting area.",
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
      "text": "The selected kind conversion violates its content/destination requirements.",
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
      "text": "The conversion error is displayed; the requested conversion is not accepted.",
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

# Edit forum — conversion refused

## Trigger

The selected kind conversion violates its content/destination requirements.

## Outcome

The conversion error is displayed; the requested conversion is not accepted.
