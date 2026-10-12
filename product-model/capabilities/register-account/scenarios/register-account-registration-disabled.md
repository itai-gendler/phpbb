---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser"
  },
  "steps": [
    {
      "text": "The User accepts the agreement and submits supplied registration input, challenge and form.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::registration"
        }
      }
    },
    {
      "text": "Registration is disabled or its activation mode requires unavailable email.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::registration"
        }
      }
    },
    {
      "text": "The registration-disabled result is displayed; no registered identity is created.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::registration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_register.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_user.php#user_add"
    }
  ]
}
---

# Register account — registration disabled

## Trigger

Registration is disabled or its activation mode requires unavailable email.

## Outcome

The registration-disabled result is displayed; no account is created.
