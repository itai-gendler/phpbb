---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "topic-subscription",
      "effect": "changes",
      "facts": [
        "Notification status"
      ],
      "contexts": [
        {
          "place": "forum-web::community::topic"
        },
        {
          "place": "forum-web::public::posting"
        },
        {
          "place": "forum-web::community::posting"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "user-permissions"
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

# Topic subscription notification status change requires the configured operation authority

The affected Account’s acting owner’s admitted read reset or configured correlated dispatch.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
