---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "category",
      "effect": "creates",
      "contexts": [
        {
          "place": "forum-web::administration::forum"
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
      "target": "phpBB/includes/acp/acp_forums.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewforum.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Category creation requires the selected administrative authority

Administrative authentication, effective a_, module entry and `a_forum` and `a_forumadd`.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.

## Kind conversion

Changing the selected existing container’s kind through Edit forum requires administrative authentication, effective a_ and a_forum, plus the implemented content/hierarchy choices. Its replacement between Forum, Category and Forum link is a conversion alternative; a_forumadd applies to a newly added container and a_forumdel to an actual deletion, not to this kind change.
