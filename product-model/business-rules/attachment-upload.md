---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "attachment",
      "effect": "creates",
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
      ],
      "to": "Uploaded"
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

# Attachment upload requires the configured operation authority

Actual admitted parent-handler authority and implemented privileged count/size exceptions; advertised upload controls are distinguished from actual request enforcement.

## Advertised controls

Posting advertises controls only with allow_attachments, u_attach, f_attach and file uploads enabled; PM controls use their corresponding enabled/attach options. Actual parser/uploader creation follows the admitted parent handler and its implemented validation, its validation and count/size checks. Anonymous poster association is shared, not a guest browser identity.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
