---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "log-entry"
    },
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "topic"
    },
    {
      "type": "entity",
      "id": "post-report"
    },
    {
      "type": "entity",
      "id": "forum"
    },
    {
      "type": "entity",
      "id": "permission-role"
    },
    {
      "type": "entity",
      "id": "user-permissions"
    },
    {
      "type": "entity",
      "id": "group-permissions"
    },
    {
      "type": "entity",
      "id": "board-settings"
    },
    {
      "type": "entity",
      "id": "account"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/log/log.php#add"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/mcp/mcp_queue.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php"
    }
  ]
}
---

# operations record actor-visible log facts

Registration/activation and account identity changes, moderation and report decisions, forum/permission/role configuration, board setting changes and log clearing record the event-specific Actor, Operation, Recorded at, IP, Category, Subject and Event information. Recording follows the enabled log category and originating handler.
