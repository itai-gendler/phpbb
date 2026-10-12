---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "topic",
      "effect": "changes",
      "facts": [
        "Approved count",
        "Unapproved count",
        "Deleted count",
        "First post",
        "Last post",
        "Last contribution",
        "Views",
        "Reported",
        "Attachments present",
        "Forum",
        "Author"
      ],
      "contexts": [
        {
          "place": "forum-web::public::topic"
        },
        {
          "place": "forum-web::community::topic"
        },
        {
          "place": "forum-web::public::posting"
        },
        {
          "place": "forum-web::community::posting"
        },
        {
          "place": "forum-web::public::post-report"
        },
        {
          "place": "forum-web::community::post-report"
        },
        {
          "place": "forum-web::community::post-review"
        },
        {
          "place": "forum-web::community::moderation-queue"
        },
        {
          "place": "forum-web::community::report-review"
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
      "target": "phpBB/posting.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php"
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

# Admitted reading and content operations maintain their topic summaries

Eligible reading or authorized correlated content/report/name effect.

## Content movement

Changing the containing Forum during accepted forum deletion/movement follows administrative authentication, a_, a_forum and a_forumdel with valid surviving destinations. This correlated operation is an alternative to contribution/read/report summary maintenance.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.

## Conversion content movement

Moving discussions out of a posting forum while configuring it as a non-posting kind follows administrative authentication, a_, a_forum and valid content destinations. The edit conversion branch does not repeat a_forumdel.

## Renamed attribution

An admitted owner username change replaces matching old retained names with nonanonymous attribution in topic author and forum/topic last-contribution summaries. This derived alternative follows the username-change authority.
