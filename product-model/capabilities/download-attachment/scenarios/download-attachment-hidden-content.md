---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User requests an existing bound contribution file with an enabled extension.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::topic"
        },
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "The bound posting area contribution is excluded by the download visibility path.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::topic"
        },
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "The download refusal/missing result is displayed without bytes.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::topic"
        },
        "community": {
          "place": "forum-web::community::topic"
        }
      }
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

# Download attachment — hidden content

## Trigger

The bound forum contribution is excluded by the download visibility path.

## Outcome

The download refusal/missing result is displayed without bytes.
