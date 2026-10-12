---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User confirms permanent deletion of the selected last contribution.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The confirmed permanent removal selects the discussion’s last remaining contribution.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The post and its containing topic are removed with dependent records; completion schedules the forum rather than a remaining discussion.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "topic",
          "effect": "removes",
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
          "entity": "forum",
          "effect": "changes",
          "facts": [
            "Topic counts",
            "Last contribution"
          ]
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
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#phpbb_handle_post_delete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_admin.php#delete_posts"
    }
  ]
}
---

# Delete post permanently — last post removes topic

## Trigger

The confirmed permanent removal selects the topic’s last remaining post.

## Outcome

The post and its containing topic are removed with dependent records; completion schedules the forum rather than a remaining discussion.
