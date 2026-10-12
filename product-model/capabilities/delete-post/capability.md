---
{
  "availability": [
    {
      "place": "forum-web::community"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#phpbb_handle_post_delete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_admin.php#delete_posts"
    }
  ]
}
---

# Delete post

The retained post becomes Deleted, deletion information and summaries/counters are synchronized, and completion schedules the remainder.
