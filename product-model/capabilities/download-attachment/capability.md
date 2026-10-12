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
      "target": "phpBB/phpbb/storage/controller/attachment.php#handle_attachment"
    }
  ]
}
---

# Download attachment

File bytes are delivered; the ordinary download branch increments Downloads, unlike thumbnail/nonincrementing paths.
