---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "facts": [
        "Last active at",
        "Online presence"
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
      "target": "phpBB/includes/functions_display.php#phpbb_show_profile"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Activity facts follow visibility preferences or online-view authority

Target visibility preferences or `u_viewonline`; online tracking/timing conditions preserved.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Hidden activity

Online visibility/allow-viewonline and u_viewonline govern hidden activity disclosure together with the implemented load/session timing conditions. A visible account and an authorized hidden-account view are alternative audiences, not a universal u_viewonline requirement.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
