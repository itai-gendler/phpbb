---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "private-message",
      "effect": "creates",
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

# Configured senders create messages for the admitted recipient set

PM enabled, `u_sendpm`; multiple/group recipients add settings and `u_masspm`/`u_masspm_group`; forwarding adds `forward_pm`/`u_pm_forward`; recipient restrictions preserved.

## Address and send authority

PMs must be enabled and u_sendpm effective. Multiple individuals require allow_mass_pm/u_masspm; groups require allow_mass_pm/u_masspm_group. Forwarding additionally requires forward_pm/u_pm_forward. Expanded recipients must have u_readpm; inactive/bot users are filtered, and Allow private messages is respected unless the sender has the implemented a_/m_ preference override. Recipient caps take applicable group maxima then board fallback. Hidden group selection is admitted through actual membership/admin filtering, distinct from recipient disclosure on an existing message.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
