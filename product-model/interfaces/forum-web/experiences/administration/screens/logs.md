---
{
  "entities": [
    {
      "entity": "log-entry",
      "shows": [
        "Actor",
        "Operation",
        "Recorded at",
        "IP",
        "Category",
        "Subject",
        "Event information"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "adm/index.php?i=logs"
    }
  ]
}
---

# Logs

The working context for logs. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
