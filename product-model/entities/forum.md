---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php#update_forum_data"
    }
  ],
  "relations": [
    {
      "entity": "forum",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "category",
      "verb": "contains child category",
      "cardinality": "one-to-many"
    },
    {
      "entity": "forum-link",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "topic",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "forum-subscription",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "user-permissions",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "group-permissions",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Forum

A posting forum containing discussions and possibly child containers.

## Information kept

- **Name** — The displayed name of this forum.
- **Description** — The kept descriptive text.
- **Parent** — The directed containing forum/category or top-level placement.
- **Order** — The relative position among sibling containers.
- **Rules** — The forum container’s rules text and formatting/link information.
- **Password protection** — The forum container’s password gate; passwords supplied for entry are request input.
- **Posting status** — The kept open/locked status used by posting admission.
- **Posting options** — The container’s configured display and contribution options.
- **Post review** — Whether intervening contributions interrupt submitted replying for review.
- **Post-count policy** — The forum contribution-count treatment consulted with the effective posting option.
- **Topic counts** — Maintained approved/pending/deleted container contribution summaries.
- **Last contribution** — The kept latest contribution identity, author and time summary.
- **Pruning settings** — The configured pruning ages/frequency and relevant options.

## Hierarchy

Parent identifies the directed parent container. A forum can contain child category instances; the opposite type can independently contain instances of this type.
