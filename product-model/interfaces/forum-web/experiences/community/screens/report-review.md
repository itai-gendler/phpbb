---
{
  "entities": [
    {
      "entity": "post-report",
      "shows": [
        "Reporter",
        "Post",
        "Reason",
        "Text",
        "Notify reporter",
        "Reported at",
        "Content snapshot",
        "Snapshot formatting"
      ]
    },
    {
      "entity": "post",
      "shows": [
        "Subject",
        "Content",
        "Author",
        "Posted at",
        "Visibility",
        "Author IP",
        "Formatting choices"
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
      "forum-web": "mcp.php?i=reports&mode=report_details"
    }
  ]
}
---

# Report review

The working context for report review. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers. Author IP has its separate information grant.
