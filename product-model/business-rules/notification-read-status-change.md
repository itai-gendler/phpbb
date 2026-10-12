---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "notification",
      "effect": "changes",
      "facts": [
        "Read status"
      ],
      "contexts": [
        {
          "place": "forum-web::community::notifications"
        },
        {
          "place": "forum-web::community::private-message"
        },
        {
          "place": "forum-web::community::topic"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "owns",
          "entity": "user"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "owns",
          "entity": "moderator"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "owns",
          "entity": "administrator"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "owns",
          "entity": "founder"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/notification/method/board.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/notification/manager.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/notification/controller/mark_read.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Notification read status change requires its account owner

Actual recipient; ownership and cutoff behavior.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
