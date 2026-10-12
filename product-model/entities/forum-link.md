---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php#update_forum_data"
    }
  ]
}
---

# Forum link

A separately addressed forum destination that can count redirects.

## Information kept

- **Name** — The displayed name of this forum link.
- **Description** — The kept descriptive text.
- **Parent** — The directed containing forum/category or top-level placement.
- **Order** — The relative position among sibling containers.
- **Rules** — The forum container’s rules text and formatting/link information.
- **Password protection** — The forum container’s password gate; passwords supplied for entry are request input.
- **Destination** — The forum link’s kept destination.
- **Track redirects** — Whether following the forum link updates its counter.
- **Redirect count** — The number of tracked follow operations.
