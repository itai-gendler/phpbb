---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "attachment",
      "effect": "removes",
      "contexts": [
        {
          "place": "forum-web::public::posting"
        },
        {
          "place": "forum-web::community::posting"
        },
        {
          "place": "forum-web::community::post-review"
        },
        {
          "place": "forum-web::community::moderation-queue"
        },
        {
          "place": "forum-web::community::private-message"
        },
        {
          "place": "forum-web::administration::forum"
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
      "target": "phpBB/phpbb/attachment/delete.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/attachment/resync.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Admitted composers or authorized parent removals remove attachments

Eligible parent operation; orphan poster check; correlated authorized content removal.

## Parser removal

The attachment action’s form proof and submitted association validate the request. A matching orphan uses the actual poster check. A bound submitted file calls deletion immediately under the admitted parent editor; later acceptance of new parent text is not required. Last-file removal synchronizes the bound Post/Topic or Private-message attachment flag.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
