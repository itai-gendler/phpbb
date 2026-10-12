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
      "text": "Agreement/form/challenge, username, email, password, timezone/profile or attempt validation fails.",
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
      "text": "The corresponding errors and retained input are shown; no registered identity is created.",
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

# Register account — invalid registration

## Trigger

Agreement/form/challenge, username, email, password, timezone/profile or attempt validation fails.

## Outcome

The corresponding errors and retained input are shown; no account is created.
