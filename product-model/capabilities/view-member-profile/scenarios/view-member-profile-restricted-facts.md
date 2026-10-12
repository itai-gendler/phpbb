---
{
  "kind": "primary",
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
      "text": "The selected profile has hidden activity or contact preferences.",
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
      "text": "The profile displays the remaining facts; raw Email and hidden activity are not treated as universally disclosed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Joined at",
            "Post count",
            "Profile values",
            "Birthday"
          ]
        }
      ],
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

# View member profile — restricted facts

## Trigger

The selected profile has hidden activity or contact preferences.

## Outcome

The profile displays the remaining facts; raw Email and hidden activity are not treated as universally disclosed.
