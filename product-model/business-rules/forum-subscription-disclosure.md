---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "forum-subscription",
      "effect": "reads",
      "contexts": [
        {
          "place": "forum-web::community::subscriptions"
        },
        {
          "place": "forum-web::community::forum"
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
      "target": "phpBB/includes/ucp/ucp_main.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#watch_topic_forum"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/posting.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Forum subscription disclosure requires its account owner

The affected Account’s acting owner; destination filtering preserved.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
