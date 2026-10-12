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
      "text": "The settings operation reaches its authority-refusal branch.",
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
      "text": "The selected settings are not changed.",
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

# Change user registration settings — authority refused

## Trigger

The settings operation reaches its authority-refusal branch.

## Outcome

The selected settings are not changed.
