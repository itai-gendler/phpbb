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
          "place": "forum-web::community::post-review"
        },
        {
          "place": "forum-web::community::moderation-queue"
        }
      ],
      "to": "Approved"
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

# Approval authority approves or restores selected queued posts

`m_approve`; covers approval and restoration.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Selected decisions

Both approval and restoration require m_approve for actual selected content. phpbb_check_ids filters forum selections; global forum zero uses the global permission decision. Already Approved entries are skipped. Restoration does not imply the poster-approval notification used for approval.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
