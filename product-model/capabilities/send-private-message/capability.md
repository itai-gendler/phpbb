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
      "target": "phpBB/includes/ucp/ucp_pm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_pm_compose.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#submit_pm"
    }
  ],
  "domain": "compose-message"
}
---

# Send private message

A Sent message, receiver copies Awaiting placement and an Available sender Outbox copy are stored; counters/time and dispatch are updated and completion schedules the new message.
