---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "message-copy",
      "effect": "changes",
      "facts": [
        "New",
        "Unread",
        "Deleted",
        "Folder"
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

# Owned reading/placement or correlated sender retraction changes copy status

Eligible owner reading/placement, or authorized correlated sender retraction.

## Per-copy outcomes

Reading an ordinary owned copy clears Unread only if it was set, and maintains the owner’s unread counter once. placement keeps its own Folder/New/Unread outcomes. Sender Outbox removal flags remaining recipient copies Deleted through the authorized originating retraction; it does not require ownership of each recipient’s copy.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
