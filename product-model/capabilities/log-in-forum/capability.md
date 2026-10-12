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
      "target": "phpBB/includes/functions.php#login_forum_box"
    }
  ]
}
---

# Log in forum

Access is recorded for the current authentication context and the intended destination resumes without a user-managed session object.
