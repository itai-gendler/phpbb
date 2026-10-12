---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "attachment",
      "effect": "changes",
      "facts": [
        "Downloads"
      ],
      "contexts": [
        {
          "place": "forum-web::public::topic"
        },
        {
          "place": "forum-web::community::topic"
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

# Attachment download counter requires the configured operation authority

Eligible download and the implemented count-increment branch.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.

## Increment branch

The counter increments only for a non-thumbnail, bound download whose effective display category is NONE. Orphan and thumbnail responses, inline-category responses, and an event-selected redirect do not run that increment.
