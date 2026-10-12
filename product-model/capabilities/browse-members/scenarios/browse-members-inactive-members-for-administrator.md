---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Administrator opens the member list.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::members"
        }
      }
    },
    {
      "text": "The administrator selects the list's inactive-member branch.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::members"
        }
      }
    },
    {
      "text": "The matching inactive accounts appear in the filtered member list.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Joined at",
            "Post count",
            "Profile values"
          ]
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::members"
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

# Browse members — inactive members for administrator

## Trigger

The administrator selects the list's inactive-member branch.

## Outcome

The matching inactive accounts appear in the filtered member list.
