---
{
  "entities": [
    {
      "entity": "forum",
      "collects": [
        "Password protection"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions.php#login_forum_box"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "viewforum.php"
    }
  ]
}
---

# Forum login

The working context for forum login. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
