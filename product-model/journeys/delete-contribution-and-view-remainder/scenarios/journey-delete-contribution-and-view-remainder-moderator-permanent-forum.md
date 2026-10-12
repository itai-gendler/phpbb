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
      "text": "The confirmed permanent removal selects the discussion’s last remaining contribution.",
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
      "text": "The post and its containing topic are removed with dependent records; completion schedules the forum rather than a remaining discussion.",
      "kind": "product",
      "actor": "moderator",
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
        "web": {
          "place": "forum-web::community::posting"
        }
      },
      "capability": "delete-post-permanently"
    },
    {
      "text": "The Product carries Moderator through the completion destination into browse discussion",
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
      "text": "The Moderator opens a posting area.",
      "kind": "actor",
      "actor": "moderator",
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
      "actor": "moderator",
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

# Delete contribution and view remainder — moderator permanent forum

## Trigger

Remove a contribution and reach the remaining discussion or forum.

## Outcome

The deletion completion destination presents the surviving discussion or forum list.
