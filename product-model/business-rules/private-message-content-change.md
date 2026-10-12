---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "private-message",
      "effect": "changes",
      "facts": [
        "Subject",
        "Content",
        "Formatting choices",
        "Edit information",
        "Attachments present"
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

# Sender-Outbox editing or retraction authority changes shared message content

Sender-Outbox editing with `u_sendpm`, `u_pm_edit` and applicable interval; or authorized sender-Outbox retraction with `u_pm_delete`.

## Edit and retract alternatives

Editing requires the actual sender’s Outbox copy, PM enabled, u_sendpm and u_pm_edit, and its configured time interval. Outbox status is the implemented condition, not proof of a recipient body read. Sender-Outbox retraction instead follows u_pm_delete and clears Content. Retraction requires u_pm_delete independently of the edit branch’s u_pm_edit.

## Derived file flag

Last-bound-file removal through an admitted message editor changes Attachments present through attachment resynchronization. This correlated alternative follows the actual attachment action; it is not conditioned on acceptance of the proposed message text.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
