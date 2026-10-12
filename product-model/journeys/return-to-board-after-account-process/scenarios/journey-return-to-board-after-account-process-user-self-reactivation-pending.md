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
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/ucp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions.php#login_box"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/provider/db.php#login"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/ucp/controller/reset_password.php#request"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/ucp/controller/reset_password.php#reset"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_profile.php"
    }
  ]
}
---

# Return to board after account process — user self reactivation pending

## Trigger

Reach the board after the account process completion.

## Outcome

The same person reaches the board index through the process completion destination.
