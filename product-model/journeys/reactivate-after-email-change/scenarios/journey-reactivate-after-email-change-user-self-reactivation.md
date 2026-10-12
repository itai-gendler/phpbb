---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User supplies the current password and a valid replacement email.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::account"
        }
      },
      "capability": "edit-account-settings"
    },
    {
      "text": "The email change selects self-reactivation with email enabled and the registered identity is not privileged identity.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::account"
        }
      },
      "capability": "edit-account-settings"
    },
    {
      "text": "Email is saved; the account becomes Inactive with activation proof, the own activation link is dispatched, current access ends and completion schedules the board.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Email",
            "Activation proof",
            "Inactivity reason"
          ],
          "to": "Inactive",
          "from": "Active"
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::account"
        }
      },
      "capability": "edit-account-settings"
    },
    {
      "text": "The Product carries User through the completion destination into browse posting area",
      "kind": "product",
      "actor": "user",
      "capability": "edit-account-settings",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::account"
        }
      }
    },
    {
      "text": "The User opens the board index.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::board-index"
        }
      },
      "capability": "browse-forums"
    },
    {
      "text": "The hierarchy displays disclosed containers and contribution summaries; hidden branches are excluded.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order",
            "Topic counts",
            "Last contribution"
          ]
        },
        {
          "entity": "category",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order"
          ]
        },
        {
          "entity": "forum-link",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::board-index"
        }
      },
      "capability": "browse-forums"
    },
    {
      "text": "The Product carries User through the completion destination into activate registered identity",
      "kind": "product",
      "actor": "user",
      "capability": "browse-forums",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::board-index"
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
    },
    {
      "text": "The Product carries User through the completion destination into browse posting area",
      "kind": "product",
      "actor": "user",
      "capability": "activate-account",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::activation"
        }
      }
    },
    {
      "text": "The User opens the board index.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::board-index"
        }
      },
      "capability": "browse-forums"
    },
    {
      "text": "The hierarchy displays disclosed containers and contribution summaries; hidden branches are excluded.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order",
            "Topic counts",
            "Last contribution"
          ]
        },
        {
          "entity": "category",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order"
          ]
        },
        {
          "entity": "forum-link",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Parent",
            "Order"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::board-index"
        }
      },
      "capability": "browse-forums"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_profile.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/index.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewforum.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#display_forums"
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

# Reactivate after email change — user self reactivation

## Trigger

Reactivate the changed-email account through its own emailed link.

## Outcome

The same account holder completes self-reactivation and reaches the board again.
