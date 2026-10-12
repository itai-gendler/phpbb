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
      "target": "phpBB/includes/message_parser.php#parse_attachments"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/attachment/upload.php"
    }
  ]
}
---

# Delete attachment

Remove the selected file through the parent composer’s attachment action. Matching orphan removal deletes its stored bytes/record; bound removal calls attachment deletion immediately and synchronizes the parent’s last-attachment flags. Removing the file does not require later acceptance of proposed parent text.
