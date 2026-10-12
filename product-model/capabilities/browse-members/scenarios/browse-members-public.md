---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest opens the member list.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::members"
        }
      }
    },
    {
      "text": "The list displays admitted account facts and supports the ordering and filtering.",
      "kind": "product",
      "actor": "guest",
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
        "web": {
          "place": "forum-web::public::members"
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

# Browse members — public

## Trigger

The visitor opens the member list.

## Outcome

The list displays admitted account facts and supports the ordering and filtering.
