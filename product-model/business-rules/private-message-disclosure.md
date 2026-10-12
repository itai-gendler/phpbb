---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "private-message",
      "effect": "reads",
      "facts": [
        "Subject",
        "Content",
        "Sender",
        "Sent at",
        "Formatting choices",
        "Edit information"
      ],
      "contexts": [
        {
          "place": "forum-web::community::private-message"
        },
        {
          "place": "forum-web::community::private-messages"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "board-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_pm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_pm_compose.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Private message disclosure requires the configured operation authority

PM enabled, `u_readpm`, permitted copy/view association and actual Held/deleted-content restrictions.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
