---
{
  "entities": [
    {
      "entity": "forum",
      "shows": [
        "Name",
        "Description",
        "Parent",
        "Order",
        "Topic counts",
        "Posting status"
      ]
    },
    {
      "entity": "category",
      "shows": [
        "Name",
        "Description",
        "Parent",
        "Order"
      ]
    },
    {
      "entity": "forum-link",
      "shows": [
        "Name",
        "Description",
        "Parent",
        "Order"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "adm/index.php?i=forums&mode=manage"
    }
  ]
}
---

# Forum management

The working context for forum management. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
