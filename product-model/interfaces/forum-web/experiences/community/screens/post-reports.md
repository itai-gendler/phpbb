---
{
  "entities": [
    {
      "entity": "post-report",
      "shows": [
        "Reporter",
        "Post",
        "Reason",
        "Reported at"
      ]
    },
    {
      "entity": "post",
      "shows": [
        "Subject",
        "Author"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/mcp/mcp_reports.php#close_report"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "mcp.php?i=reports"
    }
  ]
}
---

# Post reports

The working context for post reports. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
