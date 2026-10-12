---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "log-entry",
      "effect": "reads",
      "contexts": [
        {
          "place": "forum-web::community::moderator-logs"
        },
        {
          "place": "forum-web::administration::logs"
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
      "target": "phpBB/includes/acp/acp_logs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/mcp/mcp_logs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Moderated readable scope or administrative log-view authority discloses log entries

MCP readable/moderated scope; Administrative authentication, effective a_, module entry and `a_viewlogs`.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Scope

MCP viewing is within readable moderated forum intersections plus the handled global scope. ACP categories require administrative authentication, a_ and a_viewlogs. a_clearlogs supplies removal separately and is not a universal prerequisite for viewing.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
