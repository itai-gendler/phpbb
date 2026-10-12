---
{
  "entities": [
    {
      "entity": "forum-draft",
      "shows": [
        "Subject",
        "Saved at",
        "Forum",
        "Topic"
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

# Drafts

The working context for drafts. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
