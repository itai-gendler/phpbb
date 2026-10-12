---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator confirms valid delete-content/subforum choices.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::forum"
        }
      }
    },
    {
      "text": "The forum and selected dependent content are removed; hierarchy and summaries are synchronized. The credited authors’ account Post counts are decremented for the removed counted approved contributions.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "forum",
          "effect": "removes"
        },
        {
          "entity": "topic",
          "effect": "removes",
          "with": "forum",
          "from": "Approved"
        },
        {
          "entity": "post",
          "effect": "removes",
          "with": "topic",
          "from": "Approved"
        },
        {
          "entity": "attachment",
          "effect": "removes",
          "with": "post",
          "from": "Attached"
        },
        {
          "entity": "post-report",
          "effect": "removes",
          "with": "post",
          "from": "Open"
        },
        {
          "entity": "bookmark",
          "effect": "removes",
          "with": "topic"
        },
        {
          "entity": "topic-subscription",
          "effect": "removes",
          "with": "topic"
        },
        {
          "entity": "forum-subscription",
          "effect": "removes",
          "with": "forum"
        },
        {
          "entity": "user-permissions",
          "effect": "removes",
          "with": "forum"
        },
        {
          "entity": "group-permissions",
          "effect": "removes",
          "with": "forum"
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Post count"
          ]
        }
      ],
      "contexts": {
        "web": {
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

# Delete forum — administration

## Trigger

The administrator confirms valid delete-content/subforum choices for a container with counted approved contributions by registered authors.

## Outcome

The forum and selected dependent content are removed; hierarchy and summaries are synchronized.
