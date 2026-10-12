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
      "text": "Registration mode requires self-activation and email is available.",
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
      "text": "An Inactive account and applicable memberships are created; the self-activation link is dispatched and pending activation displayed.",
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

# Register account — self activation

## Trigger

Registration mode requires self-activation and email is available.

## Outcome

An Inactive account and applicable memberships are created; the self-activation link is dispatched and pending activation displayed.
