---
{
  "kind": "edge",
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
      "text": "The selected posting area uploaded file reaches the download path without ordinary posting area reading.",
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
      "text": "The attachment file bytes are delivered and Downloads increments on the ordinary download branch.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "attachment",
          "effect": "reads",
          "facts": [
            "Filename",
            "File content",
            "Size",
            "Media classification",
            "Binding"
          ]
        }
      ],
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
      "text": "The attachment Downloads counter increments on the ordinary download branch.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "attachment",
          "effect": "changes",
          "facts": [
            "Downloads"
          ]
        }
      ],
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

# Download attachment — download without forum read

## Trigger

The selected forum attachment reaches the download path without ordinary forum reading.

## Outcome

The file is delivered and the ordinary download counter is updated; requesting the discussion still produces its reading refusal.
