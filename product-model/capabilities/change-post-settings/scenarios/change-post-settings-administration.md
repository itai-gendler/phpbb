---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits accepted contribution settings with a valid form.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::board-settings"
        }
      }
    },
    {
      "text": "Named contribution settings are stored for subsequent core posting/display/watch behavior.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "board-settings",
          "effect": "changes",
          "facts": [
            "Posting limits",
            "Posting format settings",
            "Edit window",
            "Deletion window",
            "Flood interval",
            "Post presentation settings",
            "Bump settings",
            "Poll limit",
            "Mention settings",
            "Quick reply enabled",
            "Guest challenge",
            "Topic notifications enabled",
            "Forum notifications enabled",
            "Bookmarks enabled",
            "Censor override enabled"
          ]
        }
      ],
      "contexts": {
        "web": {
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

# Change post settings — administration

## Trigger

The administrator submits accepted Post settings with a valid form.

## Outcome

Named post settings are stored for subsequent core posting/display/watch behavior.
