---
{
  "kind": "primary",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits supplied posting area configuration without copied permissions.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::forum"
        }
      }
    },
    {
      "text": "The administrator submits valid redirecting container configuration.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::forum"
        }
      }
    },
    {
      "text": "A posting area link is created with destination/tracking configuration.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "forum-link",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order",
            "Rules",
            "Password protection",
            "Destination",
            "Track redirects",
            "Redirect count"
          ]
        }
      ],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::forum"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php"
    }
  ]
}
---

# Create forum — forum link

## Trigger

The administrator submits valid Forum link configuration.

## Outcome

A Forum link is created with destination/tracking configuration.
