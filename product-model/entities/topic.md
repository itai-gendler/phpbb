---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#submit_post"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#set_topic_visibility"
    }
  ],
  "relations": [
    {
      "entity": "post",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "bookmark",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "topic-subscription",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Topic

A discussion with a first post, subsequent contributions and visibility summaries.

## Information kept

- **Subject** — The topic title maintained from its first post.
- **Author** — The retained author identity used for attribution and decisions.
- **Forum** — The posting forum containing or intended to receive this item.
- **Created at** — When the topic was created.
- **Visibility** — The kept publication/deletion classification.
- **Posting status** — The kept open/locked status used by posting admission.
- **Topic type** — The kept discussion classification.
- **First post** — The maintained first contribution of the discussion.
- **Last post** — The maintained last contribution of the discussion.
- **Last contribution** — The kept latest contribution identity, author and time summary.
- **Approved count** — The maintained count of Approved discussion contributions.
- **Unapproved count** — The maintained pending/Reapproval required contribution count.
- **Deleted count** — The maintained soft-deleted contribution count.
- **Reported** — Whether applicable open reports remain.
- **Attachments present** — Whether this topic has bound files.
- **Views** — The discussion view counter updated by the reading branch.

## States

### Unapproved

The contribution awaits its initial publication decision.

### Approved

The contribution is approved for ordinary disclosure.

### Reapproval required

The contribution awaits approval after an applicable change.

### Deleted

The item is retained in its deleted classification.
