---
{
  "kind": "primary",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits proposed configuration for a selected posting area.",
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
      "text": "The selected posting area is converted to a grouping container using accepted content choices.",
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
      "text": "The old kind is replaced by the new independently addressed kind and applicable content movement/removal/synchronization occurs; conversion to/from links follows its valid branches.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "forum",
          "effect": "removes"
        },
        {
          "entity": "category",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order",
            "Rules",
            "Password protection"
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

# Edit forum — convert kind

## Trigger

The selected posting Forum is converted to a Category using accepted content choices.

## Outcome

The old kind is replaced by the new independently addressed kind and applicable content movement/removal/synchronization occurs; conversion to/from links follows its valid branches.
