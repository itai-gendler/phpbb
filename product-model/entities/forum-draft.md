---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/posting.php"
    }
  ],
  "domain": "manage-drafts"
}
---

# Forum draft

An account’s saved forum contribution with its intended destination.

## Information kept

- **Subject** — The saved composing subject.
- **Content** — The kept submitted text and its content representation.
- **Author** — The retained author identity used for attribution and decisions.
- **Saved at** — When the draft was saved.
- **Forum** — The posting forum containing or intended to receive this item.
- **Topic** — The forum draft’s kept topic.

## States

### Saved

The draft remains saved for its owner.
