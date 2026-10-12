---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest selects an existing member.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::member-profile"
        }
      }
    },
    {
      "text": "The selected profile displays its disclosed profile and group facts.",
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
            "Profile values",
            "Birthday"
          ]
        },
        {
          "entity": "group",
          "effect": "reads",
          "facts": [
            "Name",
            "Type"
          ]
        },
        {
          "entity": "group-membership",
          "effect": "reads",
          "facts": [
            "Account",
            "Group",
            "Default"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::member-profile"
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

# View member profile — public

## Trigger

The visitor selects an existing member.

## Outcome

The selected profile displays its disclosed profile and group facts.

## Edge cases

- An inactive selected account with INACTIVE_PROFILE can still have its profile displayed while email-change reactivation is pending.
