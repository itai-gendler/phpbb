---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "group-permissions",
      "effect": "creates",
      "contexts": [
        {
          "place": "forum-web::administration::group-permissions"
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

# Group-assignment authority or admitted new-forum copying creates group permissions

Administrative authentication, effective a_, module entry and class authority and `a_authgroups`; new-forum copy exception.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Subject and class

Assignment writes require administrative authentication, a_, the chosen a_aauth/a_uauth/a_mauth/a_fauth and a_authgroups. New-forum copy follows admitted a_forum/a_forumadd creation as its creation policy; edit copying requires a_fauth, a_authusers, a_authgroups and a_mauth.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
