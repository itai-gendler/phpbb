---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "changes",
      "facts": [
        "Subject",
        "Content",
        "Formatting choices",
        "Edit information",
        "Attachments present"
      ],
      "contexts": [
        {
          "place": "forum-web::community::posting"
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
      "target": "phpBB/posting.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Registered editors change post content through author or moderation authority

Registered edit (f_edit or m_edit; without m_edit, ownership, time and edit lock); field authority actually applied by the handler.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Registered editing

Require signed-in posting entry, f_read/password access and f_edit or m_edit. Without m_edit require the actual author, no Edit lock, and no configured edit-window expiry (post time at or before current time minus Edit window fails). Locked destinations use m_edit in edit mode. The editor applies its formatting flags and signature checks; submitted moderator edit-reason text is accepted only with m_edit.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
