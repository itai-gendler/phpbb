---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "changes",
      "facts": [
        "Visibility",
        "Deletion information"
      ],
      "contexts": [
        {
          "place": "forum-web::community::posting"
        }
      ],
      "to": "Deleted"
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

# Soft-deletion authority or the eligible author soft-deletes a post

`m_softdelete`, or registered-author deletion with latest-post, edit-lock and deletion-window checks with `f_softdelete`.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Alternatives

Effective m_softdelete admits its moderator branch. The ordinary registered-author branch requires f_softdelete, the actual author, latest-post eligibility, no Edit lock and no deletion-window expiry. f_read/password and posting entry still apply; already-Deleted content is rejected.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
