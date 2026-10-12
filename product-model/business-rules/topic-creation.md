---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "topic",
      "effect": "creates",
      "contexts": [
        {
          "place": "forum-web::public::posting"
        },
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

# Configured posting holders create topics in admitted posting forums

`f_post`, `f_read`, posting-forum and applicable lock authority.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Posting admission

Require f_read and current forum-password access, f_post and a posting-forum kind. A locked forum takes the m_edit exception for new-topic mode. Immediate publication is selected separately by f_noapprove; m_approve does not supply that option. The common board gates apply at entry.

## Flood decision

For a new contribution, u_ignoreflood or f_ignoreflood bypasses the flood interval. Otherwise compare the current request time with the signed-in account’s Last post at, or the anonymous IP’s latest post time, under Flood interval. Subject/content/form/challenge validation is separate from this authority policy.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
