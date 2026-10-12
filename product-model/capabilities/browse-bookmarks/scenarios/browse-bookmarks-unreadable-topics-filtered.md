---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens Manage saved entry.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::bookmarks"
        }
      }
    },
    {
      "text": "Some saved entries point to destinations excluded from the listing.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::bookmarks"
        }
      }
    },
    {
      "text": "Those destinations are absent from the visible list without claiming all underlying saved entries were deleted.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "bookmark",
          "effect": "reads",
          "facts": [
            "Owner",
            "Topic"
          ]
        },
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Last contribution"
          ]
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::bookmarks"
        }
      }
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

# Browse bookmarks — unreadable topics filtered

## Trigger

Some saved entries point to destinations excluded from the listing.

## Outcome

Those destinations are absent from the visible list without claiming all underlying saved entries were deleted.
