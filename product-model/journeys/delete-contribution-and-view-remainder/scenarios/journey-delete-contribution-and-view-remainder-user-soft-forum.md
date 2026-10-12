---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User confirms soft deletion of the selected contribution.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      },
      "capability": "delete-post"
    },
    {
      "text": "The last approved contribution is soft-deleted, summaries synchronized, and completion schedules the forum list",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Visibility",
            "Deletion information"
          ],
          "from": "Approved",
          "to": "Deleted"
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Approved count",
            "Deleted count",
            "First post",
            "Last post",
            "Last contribution",
            "Visibility"
          ],
          "from": "Approved",
          "to": "Deleted"
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
      "capability": "delete-post"
    },
    {
      "text": "The Product carries User through the completion destination into browse discussion",
      "kind": "product",
      "actor": "user",
      "capability": "delete-post",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The User opens a posting area.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::forum"
        }
      },
      "capability": "browse-topics"
    },
    {
      "text": "The list displays disclosed discussions with subjects, contribution summaries and paging.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Rules",
            "Topic counts",
            "Last contribution"
          ]
        },
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Created at",
            "Approved count",
            "Last contribution"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::forum"
        }
      },
      "capability": "browse-topics"
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

# Delete contribution and view remainder — user soft forum

## Trigger

Remove a contribution and reach the remaining discussion or forum.

## Outcome

The deletion completion destination presents the surviving discussion or forum list.
