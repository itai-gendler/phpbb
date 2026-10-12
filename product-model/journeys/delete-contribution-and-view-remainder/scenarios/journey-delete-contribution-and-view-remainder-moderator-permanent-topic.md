---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The Moderator confirms permanent deletion of the selected contribution.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      },
      "capability": "delete-post-permanently"
    },
    {
      "text": "The moderator confirms the selected posting deletion operation.",
      "kind": "condition",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      },
      "capability": "delete-post-permanently"
    },
    {
      "text": "The selected posting deletion and its synchronization complete through the moderator branch.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "post",
          "effect": "removes",
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
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Approved count",
            "First post",
            "Last post",
            "Last contribution",
            "Attachments present",
            "Reported"
          ]
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
        "web": {
          "place": "forum-web::community::posting"
        }
      },
      "capability": "delete-post-permanently"
    },
    {
      "text": "The Product carries Moderator through the completion destination into read discussion",
      "kind": "product",
      "actor": "moderator",
      "capability": "delete-post-permanently",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The Moderator opens an approved discussion.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The Product consults topic Subject, Author, Approved count, Last contribution",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Approved count",
            "Last contribution"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The discussion presents its disclosed contributions and author information; reading increments the applicable view summary.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Guest name",
            "Posted at",
            "Edit information",
            "Visibility",
            "Formatting choices"
          ]
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Views"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::topic"
        }
      },
      "capability": "read-topic"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#is_visible"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/index.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewforum.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#display_forums"
    }
  ]
}
---

# Delete contribution and view remainder — moderator permanent topic

## Trigger

Remove a contribution and reach the remaining discussion or forum.

## Outcome

The deletion completion destination presents the surviving discussion or forum list.
