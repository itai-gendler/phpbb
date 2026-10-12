---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a nonempty subject/content for a selected draft.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::draft"
        }
      }
    },
    {
      "text": "The selected draft has empty subject/content or invalid form input.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::draft"
        }
      }
    },
    {
      "text": "The editor shows validation errors without persisting the proposed draft change.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::draft"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ]
}
---

# Edit forum draft — invalid draft

## Trigger

The selected draft has empty subject/content or invalid form input.

## Outcome

The editor shows validation errors without persisting the proposed draft change.
