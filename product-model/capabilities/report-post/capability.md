---
{
  "availability": [
    {
      "place": "forum-web::public"
    },
    {
      "place": "forum-web::community"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/report/controller/report.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/report/report_handler_post.php"
    }
  ]
}
---

# Report post

An Open report captures content and formatting, sets reported flags and dispatches the report event; completion schedules the topic.
