---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The User accepts the agreement and submits valid registration input, challenge and form.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::registration"
        }
      }
    },
    {
      "text": "An Active account is created with applicable registered/new-member memberships and defaults; completion starts signed-in access.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
            "Username",
            "Email",
            "Credential",
            "Joined at",
            "Inactivity reason",
            "Activation proof",
            "Activation expiry",
            "Reset proof",
            "Reset expiry",
            "Credential changed at",
            "New member status",
            "Profile values",
            "Birthday",
            "Preferred language",
            "Timezone",
            "Date format",
            "Style",
            "Allow private messages",
            "Allow email contact",
            "Allow mass email",
            "Online visibility",
            "Online presence",
            "Display options",
            "Censor preference",
            "Posting defaults",
            "Notification choices",
            "Post count",
            "Last post at",
            "New message count",
            "Unread message count",
            "Last active at"
          ],
          "to": "Active"
        },
        {
          "entity": "group-membership",
          "effect": "creates",
          "facts": [
            "Account",
            "Group",
            "Pending",
            "Leader",
            "Default"
          ],
          "to": "Member",
          "with": "account"
        }
      ],
      "contexts": {
        "web": {
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

# Register account — public

## Trigger

The account holder accepts the agreement and submits valid registration input, challenge and form.

## Outcome

An Active account is created with applicable registered/new-member memberships and defaults; completion starts signed-in access.
