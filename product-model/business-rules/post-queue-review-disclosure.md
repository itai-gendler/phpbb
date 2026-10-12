---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "reads",
      "facts": [
        "Subject",
        "Content",
        "Author",
        "Guest name",
        "Posted at",
        "Visibility",
        "Formatting choices",
        "Edit information"
      ],
      "contexts": [
        {
          "place": "forum-web::community::post-review"
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
      "target": "phpBB/includes/mcp/mcp_queue.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/mcp/mcp_reports.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Approval authority reads the selected post review

`m_approve` and actual entry/selection checks.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Review selection

Use phpbb_get_post_data with m_approve and the actual visibility selection. MCP entry has signed-in/module authority and checks a supplied forum’s f_read; do not impose that same supplied-forum condition on every helper call. Author IP remains m_info.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
