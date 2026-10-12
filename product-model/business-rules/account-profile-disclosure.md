---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "facts": [
        "Username",
        "Joined at",
        "Post count",
        "Profile values",
        "Birthday"
      ],
      "contexts": [
        {
          "place": "forum-web::public::members"
        },
        {
          "place": "forum-web::public::member-profile"
        },
        {
          "place": "forum-web::community::members"
        },
        {
          "place": "forum-web::community::member-profile"
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
      "target": "phpBB/memberlist.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_profile.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Member/profile facts require the member-view or administrative authority

`u_viewprofile` or administrative alternatives; inactive-account restrictions preserved.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Member routes

The normal member/profile entry admits u_viewprofile or a_user/a_useradd/a_userdel. Bot and other inactive-profile targets require a_user or the Founder exception. An inactive target with INACTIVE_PROFILE remains visible through admitted ordinary profile entry while reactivation is pending. The list’s inactive-member branch follows its administrative account authority.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
