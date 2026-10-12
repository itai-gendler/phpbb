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
      "id": "topic-subscription"
    },
    {
      "type": "entity",
      "id": "forum-subscription"
    },
    {
      "type": "entity",
      "id": "notification"
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
      "target": "phpBB/includes/mcp/mcp_queue.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/notification/type/post.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/notification/type/topic.php"
    }
  ]
}
---

# Publication states select distinct notification dispatch paths

Approved new-topic submission dispatches the topic event and mention/quote dispatch calls; Approved reply/quote dispatches post/forum/bookmark and mention/quote calls. Unapproved new topics and replies use topic-in-queue and post-in-queue events rather than approved-publication events. Reapproval editing uses the corresponding queue event and removes the previous approve-post notification so a later approval can notify again. Preserved Unapproved edits and Deleted content do not use an approved-publication dispatch. Recipient discovery, configured preferences and available methods determine which records are kept; a dispatch call alone promises neither an external delivery nor one record for every account.
