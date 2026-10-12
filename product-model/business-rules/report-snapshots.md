---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post-report"
    },
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "topic"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/report/report_handler.php#create_report"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/report/report_handler_post.php"
    }
  ]
}
---

# Report resolution retains its captured content unless the report is removed

Submitting a Post report captures the selected post’s content and formatting with the reason, reporter, text and notification choice, and maintains the report flags on the post/topic. Closing the report changes Open to Closed and updates report flags without deleting either the post or the snapshot. Removing the report removes its retained snapshot with that report and updates flags according to remaining open reports; report resolution does not itself delete or approve the reported post.
