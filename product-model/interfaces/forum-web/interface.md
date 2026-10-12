---
{
  "type": "web",
  "actors": [
    "guest",
    "user",
    "moderator",
    "administrator",
    "founder"
  ],
  "entryPoints": [
    {
      "web": "index.php"
    },
    {
      "web": "viewforum.php"
    },
    {
      "web": "viewtopic.php"
    },
    {
      "web": "posting.php"
    },
    {
      "web": "search.php"
    },
    {
      "web": "memberlist.php"
    },
    {
      "web": "ucp.php"
    },
    {
      "web": "mcp.php"
    },
    {
      "web": "adm/index.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/index.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/ucp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/mcp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/adm/index.php"
    }
  ]
}
---

# Forum website

The browser contract offers public forum reading and account entry, the signed-in User Control Panel and Moderator Control Panel, and the Administration Control Panel. Controller downloads and AJAX outcomes serve this contract. Arrival paths are relative to the board installation.
