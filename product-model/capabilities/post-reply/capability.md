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
      "target": "phpBB/posting.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#submit_post"
    }
  ]
}
---

# Post reply

An Approved reply is stored; summaries and approved dispatch are maintained and completion points to the stored reply.
