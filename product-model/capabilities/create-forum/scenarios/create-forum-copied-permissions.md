---
{
  "kind": "primary",
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
      "text": "The administrator creates a posting area using an existing permission source.",
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
      "text": "The forum and copied member/recipient collection assignments are stored through the new-forum copy branch, which differs from edit-copy authority.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "forum",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order",
            "Rules",
            "Password protection",
            "Posting status",
            "Posting options",
            "Post review",
            "Post-count policy",
            "Topic counts",
            "Last contribution",
            "Pruning settings"
          ]
        },
        {
          "entity": "user-permissions",
          "effect": "creates",
          "with": "forum",
          "facts": [
            "Account",
            "Scope",
            "Permission class",
            "Settings",
            "Permission role"
          ]
        },
        {
          "entity": "group-permissions",
          "effect": "creates",
          "with": "forum",
          "facts": [
            "Group",
            "Scope",
            "Permission class",
            "Settings",
            "Permission role"
          ]
        }
      ],
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

# Create forum — copied permissions

## Trigger

The administrator creates a forum using an existing permission source.

## Outcome

The forum and copied user/group assignments are stored through the new-forum copy branch, which differs from edit-copy authority.
