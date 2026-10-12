---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits selected draft removal with a valid form.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::drafts"
        }
      }
    },
    {
      "text": "The selected saved drafts are removed from this registered identity's list.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-draft",
          "effect": "removes",
          "from": "Saved"
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::drafts"
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

# Delete forum draft — community

## Trigger

The account holder submits selected draft removal with a valid form.

## Outcome

The selected saved drafts are removed from this account's list.
