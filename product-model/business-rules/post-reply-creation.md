---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
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

# Configured reply holders create replies in admitted discussions

`f_reply`, `f_read`, admitted source, posting-forum and applicable lock authority.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Reply and quote admission

Require f_read, current forum-password access, f_reply and a posting-forum kind. On a locked destination, literal reply takes m_lock while quote takes m_edit. The explicit pending-source refusal applies when m_approve is effective and reply/bump selects a non-Approved topic, or quote selects a non-Approved post. Preserve the ordinary author branch admitted through Own pending visibility.

## Flood decision

u_ignoreflood or f_ignoreflood bypasses the interval. Other signed-in submissions compare current time with Last post at; anonymous submissions compare the prior post time for the IP. Preserve Flood interval using the request time.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
