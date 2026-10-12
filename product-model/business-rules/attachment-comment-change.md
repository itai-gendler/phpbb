---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "attachment",
      "effect": "changes",
      "facts": [
        "Comment"
      ],
      "contexts": [
        {
          "place": "forum-web::public::posting"
        },
        {
          "place": "forum-web::community::posting"
        },
        {
          "place": "forum-web::community::private-message"
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
      "target": "phpBB/includes/message_parser.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/storage/controller/attachment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Attachment comment change requires the configured operation authority

Authorized parent operation and submitted attachment association.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
