---
{
  "kind": "primary",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens the board index.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::board-index"
        },
        "community": {
          "place": "forum-web::community::board-index"
        }
      }
    },
    {
      "text": "The hierarchy contains a branch excluded from this listing.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::board-index"
        },
        "community": {
          "place": "forum-web::community::board-index"
        }
      }
    },
    {
      "text": "The branch and its undisclosed descendants are absent from the displayed hierarchy; other disclosed containers remain.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order",
            "Topic counts",
            "Last contribution"
          ]
        },
        {
          "entity": "category",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order"
          ]
        },
        {
          "entity": "forum-link",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order"
          ]
        }
      ],
      "contexts": {
        "public": {
          "place": "forum-web::public::board-index"
        },
        "community": {
          "place": "forum-web::community::board-index"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/index.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewforum.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#display_forums"
    }
  ]
}
---

# Browse forums — hidden branch

## Trigger

The hierarchy contains a branch excluded from this listing.

## Outcome

The branch and its undisclosed descendants are absent from the displayed hierarchy; other disclosed containers remain.
