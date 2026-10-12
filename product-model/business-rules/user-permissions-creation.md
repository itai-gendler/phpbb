---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user-permissions",
      "effect": "creates",
      "contexts": [
        {
          "place": "forum-web::administration::user-permissions"
        },
        {
          "place": "forum-web::administration::forum"
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

# Account-assignment authority or admitted new-forum copying creates user permissions

Administrative authentication, effective a_, module entry and class authority and `a_authusers`; new-forum copy exception.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Subject and class

Assignment entry and writes require administrative authentication, a_, the chosen a_aauth/a_uauth/a_mauth/a_fauth and a_authusers. New-forum copy is the distinct creation alternative: valid a_forum/a_forumadd admission can copy without the conjunction imposed on edit-time copying. Edit-time copy requires a_fauth, a_authusers, a_authgroups and a_mauth.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
