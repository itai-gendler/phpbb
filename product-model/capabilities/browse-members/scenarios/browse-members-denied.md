---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens the member list.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::members"
        },
        "community": {
          "place": "forum-web::community::members"
        }
      }
    },
    {
      "text": "The member-list request reaches its refusal branch.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::members"
        },
        "community": {
          "place": "forum-web::community::members"
        }
      }
    },
    {
      "text": "The member list is not disclosed.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::members"
        },
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

# Browse members — denied

## Trigger

The member-list request reaches its refusal branch.

## Outcome

The member list is not disclosed.
