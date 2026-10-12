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
      "verb": "contains child forum",
      "cardinality": "one-to-many"
    },
    {
      "entity": "category",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "forum-link",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Category

A separately addressed grouping container without posting-forum facts.

## Information kept

- **Name** — The displayed name of this category.
- **Description** — The kept descriptive text.
- **Parent** — The directed containing forum/category or top-level placement.
- **Order** — The relative position among sibling containers.
- **Rules** — The forum container’s rules text and formatting/link information.
- **Password protection** — The forum container’s password gate; passwords supplied for entry are request input.

## Hierarchy

Parent identifies the directed parent container. A category can contain child forum instances; the opposite type can independently contain instances of this type.
