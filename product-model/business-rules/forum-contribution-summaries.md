---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "forum",
      "effect": "changes",
      "facts": [
        "Topic counts",
        "Last contribution"
      ],
      "contexts": [
        {
          "place": "forum-web::public::posting"
        },
        {
          "place": "forum-web::community::posting"
        },
        {
          "place": "forum-web::community::post-review"
        },
        {
          "place": "forum-web::community::moderation-queue"
        },
        {
          "place": "forum-web::administration::forum"
        },
        {
          "place": "forum-web::community::account"
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
      "target": "phpBB/includes/acp/acp_forums.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewforum.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    },
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
      "target": "phpBB/includes/acp/acp_forums.php#delete_forum_content"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_user.php#user_update_name"
    }
  ]
}
---

# Authorized content operations maintain their forum contribution summaries

Authorized originating content operation or name/synchronization effect, correlated to that Forum.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.

## Renamed attribution

An admitted owner username change replaces matching old retained names with nonanonymous attribution in topic author and forum/topic last-contribution summaries. This derived alternative follows the username-change authority.
