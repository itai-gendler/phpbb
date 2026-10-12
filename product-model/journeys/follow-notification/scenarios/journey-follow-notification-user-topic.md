---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User follows a supplied non-AJAX single-board alert read link.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::notifications"
        }
      },
      "capability": "mark-notifications-read"
    },
    {
      "text": "The Product consults notification Read status",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "notification",
          "effect": "changes",
          "facts": [
            "Read status"
          ],
          "from": "Unread",
          "to": "Read"
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::notifications"
        }
      },
      "capability": "mark-notifications-read"
    },
    {
      "text": "The selected notification becomes Read and completion follows its stored destination.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "notification",
          "effect": "reads",
          "facts": [
            "Destination"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::notifications"
        }
      },
      "capability": "mark-notifications-read"
    },
    {
      "text": "The Product carries User through the completion destination into read discussion",
      "kind": "product",
      "actor": "user",
      "capability": "mark-notifications-read",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::notifications"
        }
      }
    },
    {
      "text": "The User opens an approved discussion.",
      "kind": "actor",
      "actor": "user",
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
      "actor": "user",
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
      "actor": "user",
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
      "target": "phpBB/includes/ucp/ucp_notifications.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/notification/method/board.php"
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
      "target": "phpBB/includes/ucp/ucp_pm_viewmessage.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#update_unread_status"
    }
  ]
}
---

# Follow notification — user topic

## Trigger

Follow a board notification to its corresponding content.

## Outcome

A valid non-AJAX marking link marks the notification and carries its recipient to the topic or private-message view.
