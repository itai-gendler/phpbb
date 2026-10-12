---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User supplies a file and upload action to the composer.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        },
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The upload hits the applicable count/quota/free-space limit.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        },
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The upload error is displayed and the refused upload is not stored; privileged count/size exceptions remain distinct.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        },
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

# Add attachment — quota or count refusal

## Trigger

The upload hits the applicable count/quota/free-space limit.

## Outcome

The upload error is displayed and the refused upload is not stored; privileged count/size exceptions remain distinct.
