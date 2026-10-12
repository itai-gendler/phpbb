---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "group",
      "effect": "reads",
      "contexts": [
        {
          "place": "forum-web::public::member-profile"
        },
        {
          "place": "forum-web::community::member-profile"
        },
        {
          "place": "forum-web::administration::user-permissions"
        },
        {
          "place": "forum-web::administration::group-permissions"
        },
        {
          "place": "forum-web::administration::permission-masks"
        },
        {
          "place": "forum-web::community::private-message"
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
      "target": "phpBB/phpbb/auth/auth.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/session.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/memberlist.php"
    }
  ]
}
---

# Groups are disclosed through the selected member, message or administrative policy

Actual route authority; hidden-group selection restrictions differ from already-addressed message recipient disclosure.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.

## Profile and recipient disclosure

Profile entry first follows the member-view policy. It consults only nonpending memberships. Hidden group names are disclosed when the viewer is the profile owner, holds a_group/a_groupadd/a_groupdel, or has a nonpending membership in that same group. In message viewing, To group names follow admitted message disclosure; blind group names follow the sender or nonpending-member filter in write_pm_addresses. Administrative subject lists and masks follow the corresponding subject/class or a_viewauth admission.
