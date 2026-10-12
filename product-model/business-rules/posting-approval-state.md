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
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#submit_post"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/posting.php"
    }
  ]
}
---

# Publication states follow the posting approval decision

For a new topic or reply, the effective `f_noapprove` decision yields Approved when granted and Unapproved otherwise; being a Moderator does not itself bypass approval. Editing without that option yields Reapproval required. With the option, an existing nonpublic state is preserved unless the early restoration branch has already changed Deleted to Approved. The early restoration occurs before final validation and may therefore survive a rejected edit. Explicit extension-forced visibility is outside the core decision.
