---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User saves a nonempty subject and content as a draft.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "A Saved draft keeps the registered identity and destination; completion schedules the posting area or discussion without publication.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-draft",
          "effect": "creates",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Saved at",
            "Forum",
            "Topic"
          ],
          "to": "Saved"
        }
      ],
      "contexts": {
        "web": {
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

# Save forum draft — community

## Trigger

The contributor saves a nonempty subject and content as a draft.

## Outcome

A Saved draft keeps the account and destination; completion schedules the forum or discussion without publication.
