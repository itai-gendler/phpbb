---
{
  "entities": [
    {
      "entity": "board-settings",
      "shows": [
        "Posting limits",
        "Posting format settings",
        "Edit window",
        "Deletion window",
        "Flood interval",
        "Post presentation settings",
        "Bump settings",
        "Poll limit",
        "Mention settings",
        "Quick reply enabled",
        "Guest challenge",
        "Topic notifications enabled",
        "Forum notifications enabled",
        "Bookmarks enabled",
        "Censor override enabled",
        "Registration mode",
        "New member policy",
        "Name rules",
        "Password rules",
        "Forced password age",
        "Name change enabled",
        "Email reuse enabled",
        "Registration challenge",
        "Login attempt limit",
        "Registration attempt limit",
        "COPPA settings"
      ],
      "collects": [
        "Posting limits",
        "Posting format settings",
        "Edit window",
        "Deletion window",
        "Flood interval",
        "Post presentation settings",
        "Bump settings",
        "Poll limit",
        "Mention settings",
        "Quick reply enabled",
        "Guest challenge",
        "Topic notifications enabled",
        "Forum notifications enabled",
        "Bookmarks enabled",
        "Censor override enabled",
        "Registration mode",
        "New member policy",
        "Name rules",
        "Password rules",
        "Forced password age",
        "Name change enabled",
        "Email reuse enabled",
        "Registration challenge",
        "Login attempt limit",
        "Registration attempt limit",
        "COPPA settings"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_board.php"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "adm/index.php?i=board"
    }
  ]
}
---

# Board settings

The working context for board settings. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
