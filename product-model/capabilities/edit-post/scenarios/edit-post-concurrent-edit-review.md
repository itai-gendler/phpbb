---
{
  "kind": "edge",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits proposed edits to the selected contribution.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "Review is enabled; the supplied original content checksum differs from the newer version, submitted text also differs from that newer version, and review content is available.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The editor refreshes with concurrent-change information and this final edit submission is interrupted.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Edit information"
          ]
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
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

# Edit post — concurrent edit review

## Trigger

Review is enabled; the supplied original content checksum differs from the newer version, submitted text also differs from that newer version, and review content is available.

## Outcome

The editor refreshes with concurrent-change information and this final edit submission is interrupted.

## Edge cases

- Matching the newer kept content avoids the content-checksum interruption; the separately implemented subject-checksum branch still applies.
- Without review content, the detected checksum conflict still interrupts submission; the review panel is conditional.
