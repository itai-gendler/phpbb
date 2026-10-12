---
{
  "kind": "primary",
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
      "text": "The age/agreement route selects COPPA registration.",
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
      "text": "An Inactive account is created with COPPA membership/default behavior and the COPPA completion/instructions.",
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
          "to": "Inactive"
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

# Register account — coppa inactive

## Trigger

The age/agreement route selects COPPA registration.

## Outcome

An Inactive account is created with COPPA membership/default behavior and the COPPA completion/instructions.
