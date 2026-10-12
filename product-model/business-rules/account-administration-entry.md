---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "facts": [
        "Username",
        "Credential",
        "Inactivity reason"
      ],
      "contexts": [
        {
          "place": "forum-web::community::login"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "user-permissions"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions.php#login_box"
    }
  ]
}
---

# Account administration entry requires the configured operation authority

Effective `a_` and eligible administrative identity; password authentication remains separate.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.
