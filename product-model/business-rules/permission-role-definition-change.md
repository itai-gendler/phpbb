---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "permission-role",
      "effect": "changes",
      "facts": [
        "Name",
        "Description",
        "Permission class",
        "Settings"
      ],
      "contexts": [
        {
          "place": "forum-web::administration::permission-role"
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
      "target": "phpBB/includes/acp/acp_permissions.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_permission_roles.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/auth.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Role and selected-class authority edits permission definitions

Same authority; header persistence preceding settings refusal remains observable.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Header persistence

Role administration requires administrative authentication, a_, a_roles and selected a_aauth/a_uauth/a_mauth/a_fauth. Name/description/header writes precede filtering submitted settings to the class; an empty filtered set triggers WRONG_PERMISSION_SETTING_FORMAT after that header write.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
