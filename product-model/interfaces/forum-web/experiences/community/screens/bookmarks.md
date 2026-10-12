---
{
  "entities": [
    {
      "entity": "bookmark",
      "shows": [
        "Owner",
        "Topic"
      ]
    },
    {
      "entity": "topic",
      "shows": [
        "Subject",
        "Last contribution"
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
      "forum-web": "ucp.php?i=main&mode=bookmarks"
    }
  ]
}
---

# Bookmarks

The working context for bookmarks. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
