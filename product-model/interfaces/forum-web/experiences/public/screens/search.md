---
{
  "entities": [
    {
      "entity": "topic",
      "shows": [
        "Subject",
        "Author",
        "Created at",
        "Last contribution"
      ]
    },
    {
      "entity": "post",
      "shows": [
        "Subject",
        "Content",
        "Author",
        "Posted at"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/search.php"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "search.php"
    }
  ]
}
---

# Search

The working context for search. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers. Search criteria are transient query input, not kept Entity facts.
