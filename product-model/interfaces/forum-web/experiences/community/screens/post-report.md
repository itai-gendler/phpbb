---
{
  "entities": [
    {
      "entity": "post",
      "shows": [
        "Subject",
        "Content",
        "Formatting choices"
      ]
    },
    {
      "entity": "post-report",
      "collects": [
        "Reason",
        "Text",
        "Notify reporter"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/report/controller/report.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/report/report_handler_post.php"
    }
  ]
}
---

# Post report

The working context for post report. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
