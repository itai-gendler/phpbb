---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens Manage saved entry.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::bookmarks"
        }
      }
    },
    {
      "text": "The list displays this registered identity's saved entries whose topics survive filtering.",
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
        "web": {
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

# Browse bookmarks — community

## Trigger

The account holder opens Manage bookmarks.

## Outcome

The list displays this account's saved entries whose topics survive filtering.
