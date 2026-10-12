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
      "target": "phpBB/phpbb/content_visibility.php#set_post_visibility"
    }
  ],
  "relations": [
    {
      "entity": "attachment",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "post-report",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Post

A contribution whose content, publication state and author information are kept.

## Information kept

- **Subject** — The post subject entered by its contributor.
- **Content** — The kept submitted text and its content representation.
- **Author** — The retained author identity used for attribution and decisions.
- **Guest name** — The supplied guest attribution text for anonymous posting.
- **Posted at** — The kept contribution posting time.
- **Author IP** — The recorded posting address, separately governed during moderation disclosure.
- **Formatting choices** — The kept BBCode/link/smiley/signature choices used in presentation.
- **Edit information** — The retained editor/time/reason/count information from the applicable edit path.
- **Edit lock** — The retained lock used by ordinary-author editing/deletion checks.
- **Visibility** — The kept publication/deletion classification.
- **Deletion information** — The deleting identity, time and reason retained on soft deletion.
- **Count contribution** — Whether this contribution participates in its author’s post count.
- **Reported** — Whether applicable open reports remain.
- **Attachments present** — Whether this post has bound files.

## States

### Unapproved

The contribution awaits its initial publication decision.

### Approved

The contribution is approved for ordinary disclosure.

### Reapproval required

The contribution awaits approval after an applicable change.

### Deleted

The item is retained in its deleted classification.
