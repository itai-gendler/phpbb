---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User opens the requested discussion.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The configured credential age intercepts this signed-in request.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The Product carries the account holder to Edit account settings before displaying the requested discussion.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Credential changed at"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The Product carries User through the completion destination into edit registered identity settings",
      "kind": "product",
      "actor": "user",
      "capability": "read-topic",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "The User supplies the current password and matching valid replacement passwords.",
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
      "text": "The Product carried the registered identity holder here through the configured password-age continuation.",
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
      "text": "Accepted replacement changes Credential and Credential changed at and completes the required change.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Credential",
            "Credential changed at"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::account"
        }
      },
      "capability": "edit-account-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#is_visible"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_profile.php"
    }
  ]
}
---

# Change required account password — user required change

## Trigger

Complete the credential change required while entering a discussion.

## Outcome

The account holder reaches Edit account settings through the interception and saves a valid replacement.
