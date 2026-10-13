---
{
  "id": "phpbb",
  "summary": "A configurable forum website for discussions, private messages and community administration.",
  "category": "forum-software",
  "authors": [
    {
      "name": "phpBB Limited",
      "url": "https://www.phpbb.com/"
    }
  ],
  "license": "GPL-2.0-only",
  "languages": [
    "en"
  ],
  "limitations": [
    "Private messages are exchanged among registered users only.",
    "Without moderator authority, authors edit their posts only within the board's edit time limit and delete them only while they are still the topic's last post.",
    "The core package serves English; boards add other languages, styles and extensions as separately installed packages."
  ],
  "references": [
    {
      "kind": "code",
      "role": "context",
      "target": "phpBB/composer.json"
    },
    {
      "kind": "doc",
      "role": "context",
      "target": "phpBB/docs/LICENSE.txt"
    }
  ]
}
---

# phpBB

phpBB provides forums and topics in which visitors and registered users read and contribute posts. Accounts keep personal preferences, saved discussions and drafts, messages and notifications. Configured moderators decide publication and reports; administrators configure forums, permissions, permission roles, logs and board settings. The core browser contract distinguishes public access, the signed-in community and administration.

## Intent

phpBB is a free, open-source bulletin board. It gives a community its own discussion site, where members talk in forums and topics and the board's own moderators and administrators run it from control panels.
