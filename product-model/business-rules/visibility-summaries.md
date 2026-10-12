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
      "id": "forum"
    },
    {
      "type": "entity",
      "id": "account"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#submit_post"
    }
  ]
}
---

# Visibility effects maintain contribution summaries without own-pending count parity

New Topic creation keeps its First post and Last post even when its initial Post is queued. New queued replies increment Unapproved count without replacing the existing Topic Last post/Last contribution or Forum Last contribution; accepted Approved replies maintain those summaries. Approved publication updates the account Post count only under the effective f_postcount decision, while submitting new content updates Last post at. The visibility helper maintains approved, unapproved and deleted counters and the appropriate first/last summaries on approval, restoration, soft deletion and reapproval. An ordinary author’s own pending visibility does not turn pending content into Approved counts.
