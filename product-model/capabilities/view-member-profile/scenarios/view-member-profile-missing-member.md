---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User selects an existing member.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::member-profile"
        },
        "community": {
          "place": "forum-web::community::member-profile"
        }
      }
    },
    {
      "text": "The selected registered identity does not exist.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::member-profile"
        },
        "community": {
          "place": "forum-web::community::member-profile"
        }
      }
    },
    {
      "text": "The missing-member result is displayed without profile output.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::member-profile"
        },
        "community": {
          "place": "forum-web::community::member-profile"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/memberlist.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#phpbb_show_profile"
    }
  ]
}
---

# View member profile — missing member

## Trigger

The selected account does not exist.

## Outcome

The missing-member result is displayed without profile output.
