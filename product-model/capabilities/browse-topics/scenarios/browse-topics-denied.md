---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens a posting area.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::forum"
        },
        "community": {
          "place": "forum-web::community::forum"
        }
      }
    },
    {
      "text": "The selected posting area request reaches the refusal branch.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::forum"
        },
        "community": {
          "place": "forum-web::community::forum"
        }
      }
    },
    {
      "text": "The list is not disclosed and the route displays its authentication/refusal result.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::forum"
        },
        "community": {
          "place": "forum-web::community::forum"
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

# Browse topics — denied

## Trigger

The selected forum request reaches the refusal branch.

## Outcome

The list is not disclosed and the route displays its authentication/refusal result.
