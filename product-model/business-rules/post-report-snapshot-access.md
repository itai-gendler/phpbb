---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post",
      "effect": "reads",
      "facts": [
        "Subject",
        "Content",
        "Formatting choices"
      ],
      "contexts": [
        {
          "place": "forum-web::public::post-report"
        },
        {
          "place": "forum-web::community::post-report"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "user-permissions"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/report/report_handler_post.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Report authority reads the source facts used for its snapshot

`f_list`, `f_read`, `f_report`; no invented Visibility (Approved, an admitted author’s own pending content under the setting, or m_approve; Deleted has no ordinary-author exception)/password guard.

## Effective decision

The grant reads effective configured authority for the actual acting identity and selected forum or global scope. It combines the actual direct assignments, assigned permission roles and eligible group assignments using the Effective permissions Rule. Fixed role names alone confer no authority.

## Snapshot source

Report submission requires f_list, f_read and f_report and an existing unreported post. The handler does not repeat ordinary post Visibility or forum-password entry; the stored snapshot therefore follows this source path, including nonpublic selections.

## Entry availability

Where this operation enters through user setup, the disabled-board audience is selected as administrators only (effective a_), administrators plus global moderators (a_ or global m_), or administrators plus global/local moderators (a_ or m_ or a local m_). IN_LOGIN/installation/explicit skip paths retain their disabled-board exemptions. Exceeded Load limit excludes ordinary requests while administrative/global/local moderation authority and IN_LOGIN/IN_ADMIN keep the implemented exceptions. These entry checks do not undo an effect already persisted later in the request.
