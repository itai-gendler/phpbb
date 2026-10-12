---
{
  "entities": [
    {
      "entity": "forum-draft",
      "shows": [
        "Subject",
        "Content",
        "Saved at",
        "Forum",
        "Topic"
      ],
      "collects": [
        "Subject",
        "Content"
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
      "forum-web": "ucp.php?i=main&mode=drafts"
    }
  ]
}
---

# Draft

The working context for draft. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
