---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Credential",
        "Credential changed at"
      ],
      "contexts": [
        {
          "place": "forum-web::community::account"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "user"
        }
      ],
      "configuredBy": "user-permissions"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "moderator"
        }
      ],
      "configuredBy": "user-permissions"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "administrator"
        }
      ],
      "configuredBy": "user-permissions"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "founder"
        }
      ],
      "configuredBy": "user-permissions"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_profile.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_prefs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Account password change requires its account owner

The affected Account’s acting owner and `u_chgpasswd`.

## Field authority

The ownership grants additionally require the effective field option stated above. The effective option is resolved through the direct/group/role aggregation, not through a kept Account permission flag.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
