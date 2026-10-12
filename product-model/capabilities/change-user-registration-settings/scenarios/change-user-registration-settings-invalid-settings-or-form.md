---
{
  "kind": "validation",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits proposed member registration settings with a supplied form.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::board-settings"
        }
      }
    },
    {
      "text": "A selected value or settings form fails validation.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::board-settings"
        }
      }
    },
    {
      "text": "The settings process displays errors and the proposed settings are not stored.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::board-settings"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_board.php"
    }
  ]
}
---

# Change user registration settings — invalid settings or form

## Trigger

A selected value or settings form fails validation.

## Outcome

The settings process displays errors and the proposed settings are not stored.
