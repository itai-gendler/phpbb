---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "forum",
      "effect": "reads",
      "contexts": [
        {
          "place": "forum-web::public::board-index"
        },
        {
          "place": "forum-web::public::forum"
        },
        {
          "place": "forum-web::community::board-index"
        },
        {
          "place": "forum-web::community::forum"
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

# Listing or admitted forum-entry authority discloses the corresponding forum facts

Actual route’s listing/read/title-list checks and password access; not a universal conjunction of all three ACL options.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Listing versus entry

Board hierarchy disclosure follows f_list for each listed container. Selected posting-forum entry admits f_list OR f_list_topics OR f_read; protected entry then requires current forum access. f_list_topics can supply titles when ordinary reading is absent. Passwords do not hide every index metadata fact.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
