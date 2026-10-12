---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "topic"
    },
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "forum-draft"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#submit_post"
    }
  ]
}
---

# Stored contributions consume the loaded owner draft

When topic/reply submission supplies draft_loaded, submission deletes that addressed Forum draft only when it belongs to the acting account. Consumption follows committed contribution storage and precedes search indexing. Opening or loading a draft alone does not consume it, and a refused form that never stores the contribution leaves it Saved.
