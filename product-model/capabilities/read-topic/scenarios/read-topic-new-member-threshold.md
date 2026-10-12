---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens an approved discussion.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "The signed-in registered identity reaches its configured new-member threshold.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "The newly registered membership is removed and the account's new-member/default dependencies adjusted; reading then continues.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "group-membership",
          "effect": "removes",
          "from": "Member"
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "New member status"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Visibility"
          ]
        }
      ],
      "contexts": {
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
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#is_visible"
    }
  ]
}
---

# Read topic — new member threshold

## Trigger

The signed-in account reaches its configured new-member threshold.

## Outcome

The newly registered membership is removed and the account's new-member/default dependencies adjusted; reading then continues.
