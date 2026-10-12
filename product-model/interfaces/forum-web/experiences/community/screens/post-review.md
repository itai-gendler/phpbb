---
{
  "entities": [
    {
      "entity": "topic",
      "shows": [
        "Subject",
        "Visibility"
      ]
    },
    {
      "entity": "post",
      "shows": [
        "Subject",
        "Content",
        "Author",
        "Guest name",
        "Posted at",
        "Visibility",
        "Formatting choices",
        "Author IP",
        "Edit information"
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
      "forum-web": "mcp.php?i=queue&mode=approve_details"
    }
  ]
}
---

# Post review

The working context for post review. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers. Author IP has its separate information grant.
