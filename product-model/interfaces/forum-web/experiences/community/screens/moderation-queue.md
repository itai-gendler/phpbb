---
{
  "entities": [
    {
      "entity": "topic",
      "shows": [
        "Subject",
        "Author",
        "Visibility"
      ]
    },
    {
      "entity": "post",
      "shows": [
        "Subject",
        "Author",
        "Posted at",
        "Visibility"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/mcp/mcp_queue.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_mcp.php#phpbb_check_ids"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "mcp.php?i=queue"
    }
  ]
}
---

# Moderation queue

The working context for moderation queue. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
