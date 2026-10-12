---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "facts": [
        "Email"
      ],
      "contexts": [
        {
          "place": "forum-web::community::account"
        },
        {
          "place": "forum-web::public::member-profile"
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

# Email is disclosed to its account owner or the admitted raw-contact audience

The affected Account’s acting owner account settings; or permitted raw-email contact disclosure. Email-form URLs are not raw-email disclosure.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Raw contact disclosure

On member/profile output, a mail contact is admitted by Allow email contact with u_sendemail, or a_user. board_email_form with Email enabled produces an email-form URL rather than exposing Email. Otherwise board_hide_emails suppresses raw mailto disclosure except for a_user. Own account settings disclose the account’s Email.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
