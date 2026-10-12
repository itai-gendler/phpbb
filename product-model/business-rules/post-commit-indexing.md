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

# Search indexing may fail after contribution storage commits

submit_post commits the content transaction before consuming the supplied loaded owner draft and before resolving/calling the configured search backend. A missing search module or indexing failure can therefore produce an error after Topic/Post storage, attachment binding and summary maintenance persist. The completion redirect and later submission notification dispatch are not reached on that failure; no rollback of already committed content or consumed draft is promised.
