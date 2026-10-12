---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The Founder submits supplied posting area configuration without copied permissions.",
      "kind": "actor",
      "actor": "founder",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::forum"
        }
      },
      "capability": "create-forum"
    },
    {
      "text": "A forum is created; the creation branch can schedule forum-permission assignment, otherwise completion shows the creation result.",
      "kind": "product",
      "actor": "founder",
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
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::administration::forum"
        }
      },
      "capability": "create-forum"
    },
    {
      "text": "The Product carries Founder through the completion destination into add direct identity assignment",
      "kind": "product",
      "actor": "founder",
      "capability": "create-forum",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::forum"
        }
      }
    },
    {
      "text": "The Founder selects the created scope and submits the desired assignment options for the chosen subjects.",
      "kind": "actor",
      "actor": "founder",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::user-permissions"
        }
      },
      "capability": "add-user-permissions"
    },
    {
      "text": "The Founder selects valid subjects and a posting area-local permission class/scope.",
      "kind": "condition",
      "actor": "founder",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::user-permissions"
        }
      },
      "capability": "add-user-permissions"
    },
    {
      "text": "The selected posting area-scoped assignments follow the requested operation; global assignments outside that selection remain.",
      "kind": "product",
      "actor": "founder",
      "entities": [
        {
          "entity": "user-permissions",
          "effect": "creates",
          "facts": [
            "Account",
            "Scope",
            "Permission class",
            "Settings",
            "Permission role"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::administration::user-permissions"
        }
      },
      "capability": "add-user-permissions"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_permissions.php#set_permissions"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/auth.php#acl_set"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/auth.php#acl_delete"
    }
  ]
}
---

# Create forum and assign permissions — founder user

## Trigger

Create a forum and establish its first selected permission assignment.

## Outcome

The creation branch schedules the permission destination and the same administrator completes a selected user/group assignment.
