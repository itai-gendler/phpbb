---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "attachment",
      "effect": "reads",
      "facts": [
        "Filename",
        "File content",
        "Size",
        "Media classification",
        "Binding"
      ],
      "contexts": [
        {
          "place": "forum-web::public::topic"
        },
        {
          "place": "forum-web::community::topic"
        },
        {
          "place": "forum-web::community::private-message"
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
      "target": "phpBB/includes/message_parser.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/storage/controller/attachment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Download policy admits file reads through feature, linkage and content-specific authority

Forum: `u_download`, `f_download`, topic/post Visibility (Approved, an admitted author’s own pending content under the setting, or m_approve; Deleted has no ordinary-author exception) and password. PM: `u_pm_download` and sender/copy association. Orphan: matching poster identity or `a_attach`, plus applicable download permission.

## Feature and linkage admission

The actual Use selects allow_attachments versus allow_pm_attach. Secure download settings also call download_allowed: when secure_downloads is enabled, missing/malformed Referer follows secure_allow_empty_referer; an own-server hostname is admitted; otherwise the hostname/resolved-IP site list and allow/deny/exclusion mode determine linkage. A refused link returns LINKAGE_FORBIDDEN before bytes. Attachment settings determine this linkage policy.

## Bound and orphan paths

Forum files require u_download/f_download, topic and post Visibility, and current protected-forum access; f_read is not a repeated download requirement. PM files require u_pm_download plus sender/copy association or supplied authorization-ID path, without an extra u_readpm requirement. Orphans require matching poster identity or a_attach, then the use-specific download option. Anonymous matching uses shared anonymous identity. Enabled extension, actual storage existence and filename/linkage validation retain their observed failures.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
