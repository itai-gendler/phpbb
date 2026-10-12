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
      "text": "The profile request reaches its refusal branch.",
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
      "text": "The member profile is not disclosed.",
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

# View member profile — denied

## Trigger

The profile request reaches its refusal branch.

## Outcome

The member profile is not disclosed.
