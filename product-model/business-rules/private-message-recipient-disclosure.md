---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "private-message",
      "effect": "reads",
      "facts": [
        "To recipients",
        "Blind-copy recipients"
      ],
      "contexts": [
        {
          "place": "forum-web::community::private-message"
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

# Private message recipient disclosure requires the configured operation authority

To recipients follow eligible message viewing. Individual blind recipients are shown to sender or themselves; blind Group recipients follow the sender/member filtering.

## Recipient filtering

This read operation discloses the filtered addressing projection only. The sender sees blind individual recipients; an individual sees their own blind address. Blind group names use the actual sender/member filtering in write_pm_addresses. A filtered view never means disclosure of the unfiltered kept set.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
