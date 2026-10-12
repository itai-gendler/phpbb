---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
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
      },
      "capability": "register-account"
    },
    {
      "text": "Registration mode requires self-activation and email is available.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::registration"
        }
      },
      "capability": "register-account"
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
        "web": {
          "place": "forum-web::public::registration"
        }
      },
      "capability": "register-account"
    },
    {
      "text": "The Product carries User through the completion destination into activate registered identity",
      "kind": "product",
      "actor": "user",
      "capability": "register-account",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::registration"
        }
      }
    },
    {
      "text": "The User follows the self-activation link with the entered registered identity and key.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::activation"
        }
      },
      "capability": "activate-account"
    },
    {
      "text": "The account becomes Active, its activation proof is cleared and completion schedules the board destination.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Inactivity reason",
            "Activation proof",
            "Reset proof",
            "Reset expiry"
          ],
          "from": "Inactive",
          "to": "Active"
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::activation"
        }
      },
      "capability": "activate-account"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_activate.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_user.php#user_active_flip"
    }
  ]
}
---

# Register and activate account — user self activation

## Trigger

Obtain an activated forum account through the self-activation link.

## Outcome

The created inactive identity becomes Active after the same account holder follows the dispatched link.
