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
      "text": "The selected download reaches its authority-refusal branch.",
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
      "text": "No file bytes are delivered.",
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

# Download attachment — permission refused

## Trigger

The selected download reaches its authority-refusal branch.

## Outcome

No file bytes are delivered.

## Edge cases

- A configured secure-download linkage refusal produces LINKAGE_FORBIDDEN before delivering any bytes.
