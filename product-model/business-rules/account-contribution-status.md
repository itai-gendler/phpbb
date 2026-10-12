---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Post count",
        "Last post at",
        "New member status"
      ],
      "contexts": [
        {
          "place": "forum-web::public::posting"
        },
        {
          "place": "forum-web::community::posting"
        },
        {
          "place": "forum-web::community::moderation-queue"
        },
        {
          "place": "forum-web::community::post-review"
        },
        {
          "place": "forum-web::community::topic"
        },
        {
          "place": "forum-web::administration::forum"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "board-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#submit_post"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/session.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php#delete_forum_content"
    }
  ]
}
---

# Account contribution status requires the configured operation authority

Authorized originating contribution/visibility effect, or the owner’s configured new-member threshold effect.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.

## Container content removal

Removing counted approved contributions through a permitted container deletion or kind-conversion content action adjusts their actual authors’ Post count. Container deletion follows a_forum/a_forumdel; edit-time conversion follows a_forum and its accepted content choices.
