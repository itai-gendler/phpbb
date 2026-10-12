---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User submits a nonempty subject/content for a selected draft.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::draft"
        }
      },
      "capability": "edit-forum-draft"
    },
    {
      "text": "The saved draft is changed and completion schedules Manage drafts.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-draft",
          "effect": "changes",
          "facts": [
            "Subject",
            "Content"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::draft"
        }
      },
      "capability": "edit-forum-draft"
    },
    {
      "text": "The Product carries User through the completion destination into browse posting area drafts",
      "kind": "product",
      "actor": "user",
      "capability": "edit-forum-draft",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::draft"
        }
      }
    },
    {
      "text": "The User opens Manage drafts.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::drafts"
        }
      },
      "capability": "browse-forum-drafts"
    },
    {
      "text": "The list displays this registered identity's saved posting area drafts and available composing destinations.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-draft",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Saved at",
            "Forum",
            "Topic"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::drafts"
        }
      },
      "capability": "browse-forum-drafts"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ]
}
---

# Edit draft and return to drafts — user edit

## Trigger

Save the selected draft and reach Manage drafts.

## Outcome

The account holder follows the saved-editor completion destination to the draft list.
