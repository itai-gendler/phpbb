---
{
  "scope": "Inspected core browser entry points, handlers, persistence, authorization and selected administrative sections at a57d60d390ede790e0b49995a4a3d581acaf1989.",
  "method": "Static read-only source tracing with shipped declarations, names, templates and selected documentation/test-source corroboration.",
  "covered": [
    {
      "description": "Forum index and reading controllers and their display/visibility branches",
      "paths": [
        "phpBB/index.php",
        "phpBB/phpbb/forum/controller/index.php",
        "phpBB/viewforum.php",
        "phpBB/viewtopic.php",
        "phpBB/includes/functions_display.php",
        "phpBB/phpbb/content_visibility.php"
      ]
    },
    {
      "description": "Search and member disclosure branches",
      "paths": [
        "phpBB/search.php",
        "phpBB/memberlist.php"
      ]
    },
    {
      "description": "Topic/reply submission, edit/deletion, draft consumption and dependent content helpers",
      "paths": [
        "phpBB/posting.php",
        "phpBB/includes/functions_posting.php",
        "phpBB/includes/functions_admin.php"
      ]
    },
    {
      "description": "Saved forum lists and draft branches in UCP main",
      "paths": [
        "phpBB/includes/ucp/ucp_main.php",
        "phpBB/includes/ucp/info/ucp_main.php"
      ]
    },
    {
      "description": "Attachment parsing, upload validation, binding/removal and download authorization",
      "paths": [
        "phpBB/includes/message_parser.php",
        "phpBB/phpbb/attachment/",
        "phpBB/phpbb/storage/controller/attachment.php"
      ]
    },
    {
      "description": "Registration, activation, database authentication, reset and common access gates",
      "paths": [
        "phpBB/ucp.php",
        "phpBB/includes/ucp/ucp_register.php",
        "phpBB/includes/ucp/ucp_activate.php",
        "phpBB/phpbb/ucp/controller/reset_password.php",
        "phpBB/includes/functions_user.php",
        "phpBB/includes/functions.php",
        "phpBB/phpbb/auth/provider/db.php",
        "phpBB/phpbb/user.php",
        "phpBB/phpbb/session.php"
      ]
    },
    {
      "description": "Account identity/profile and personal preference sections",
      "paths": [
        "phpBB/includes/ucp/ucp_profile.php",
        "phpBB/includes/ucp/ucp_prefs.php",
        "phpBB/includes/ucp/info/ucp_profile.php",
        "phpBB/includes/ucp/info/ucp_prefs.php"
      ]
    },
    {
      "description": "Private-message composing, mailbox/viewing and copy/content helpers",
      "paths": [
        "phpBB/includes/ucp/ucp_pm.php",
        "phpBB/includes/ucp/ucp_pm_compose.php",
        "phpBB/includes/ucp/ucp_pm_viewfolder.php",
        "phpBB/includes/ucp/ucp_pm_viewmessage.php",
        "phpBB/includes/functions_privmsgs.php"
      ]
    },
    {
      "description": "Notification options, board method, marking controller and inspected post/topic/PM event branches",
      "paths": [
        "phpBB/includes/ucp/ucp_notifications.php",
        "phpBB/phpbb/notification/manager.php",
        "phpBB/phpbb/notification/method/board.php",
        "phpBB/phpbb/notification/controller/mark_read.php",
        "phpBB/phpbb/notification/type/base.php",
        "phpBB/phpbb/notification/type/post.php",
        "phpBB/phpbb/notification/type/topic.php",
        "phpBB/phpbb/notification/type/pm.php"
      ]
    },
    {
      "description": "Queue approval/restoration/disapproval and post-report submission/resolution",
      "paths": [
        "phpBB/mcp.php",
        "phpBB/includes/functions_mcp.php",
        "phpBB/includes/mcp/mcp_queue.php",
        "phpBB/includes/mcp/mcp_reports.php",
        "phpBB/phpbb/report/controller/report.php",
        "phpBB/phpbb/report/report_handler.php",
        "phpBB/phpbb/report/report_handler_post.php"
      ]
    },
    {
      "description": "Forum containers, assignment/role administration and effective ACL resolution",
      "paths": [
        "phpBB/adm/index.php",
        "phpBB/includes/acp/acp_forums.php",
        "phpBB/includes/acp/acp_permissions.php",
        "phpBB/includes/acp/acp_permission_roles.php",
        "phpBB/includes/acp/auth.php",
        "phpBB/phpbb/auth/auth.php"
      ]
    },
    {
      "description": "Post/registration board settings and actor-visible log handlers",
      "paths": [
        "phpBB/includes/acp/acp_board.php",
        "phpBB/includes/acp/acp_logs.php",
        "phpBB/includes/mcp/mcp_logs.php",
        "phpBB/phpbb/log/log.php"
      ]
    },
    {
      "description": "Shipped naming, fact disclosure and interaction wiring corroborating inspected handlers",
      "paths": [
        "phpBB/language/en/",
        "phpBB/styles/prosilver/template/",
        "phpBB/adm/style/",
        "phpBB/composer.json"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Development environments, CI/build and contribution tooling",
      "paths": [
        ".devcontainer/",
        ".github/",
        "build/",
        "git-tools/",
        "vagrant/",
        ".vscode/"
      ]
    },
    {
      "description": "Test harnesses and fixtures used only as static corroboration",
      "paths": [
        "tests/"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "Feed and operator command contracts",
      "paths": [
        "phpBB/phpbb/feed/",
        "phpBB/phpbb/console/command/"
      ]
    },
    {
      "description": "Installation, updating, conversion and backup/restore tooling",
      "paths": [
        "phpBB/install/",
        "phpBB/phpbb/install/",
        "phpBB/includes/acp/acp_database.php"
      ]
    },
    {
      "description": "Other authentication providers, OAuth linking and legacy password activation",
      "paths": [
        "phpBB/phpbb/auth/provider/",
        "phpBB/includes/ucp/ucp_auth_link.php",
        "phpBB/includes/ucp/ucp_activate.php"
      ]
    },
    {
      "description": "Broader account/group administration, deletion, signatures/avatars and remembered-key management",
      "paths": [
        "phpBB/includes/acp/acp_users.php",
        "phpBB/includes/acp/acp_groups.php",
        "phpBB/includes/ucp/ucp_groups.php",
        "phpBB/includes/ucp/ucp_profile.php",
        "phpBB/includes/functions_user.php",
        "phpBB/phpbb/session.php"
      ]
    },
    {
      "description": "Polls, manual read marking, standalone preview and full formatting permissions",
      "paths": [
        "phpBB/posting.php",
        "phpBB/viewtopic.php",
        "phpBB/viewforum.php",
        "phpBB/includes/message_parser.php",
        "phpBB/includes/functions_display.php"
      ]
    },
    {
      "description": "Lock/bump/move/copy/split/merge/type operations and queue permanent-delete dispatch",
      "paths": [
        "phpBB/includes/mcp/mcp_main.php",
        "phpBB/includes/mcp/mcp_queue.php",
        "phpBB/posting.php"
      ]
    },
    {
      "description": "Remaining private-message folders/rules/capacity/release, drafts/reports and marked-message actions",
      "paths": [
        "phpBB/includes/ucp/ucp_pm.php",
        "phpBB/includes/ucp/ucp_pm_options.php",
        "phpBB/includes/functions_privmsgs.php",
        "phpBB/phpbb/report/report_handler_pm.php"
      ]
    },
    {
      "description": "Warnings/bans/notes/contact/email and online/help/cookie surfaces",
      "paths": [
        "phpBB/includes/mcp/",
        "phpBB/memberlist.php",
        "phpBB/phpbb/controller/"
      ]
    },
    {
      "description": "Standalone permission copying/impersonation and unusual cross-class role requests",
      "paths": [
        "phpBB/includes/acp/acp_permissions.php",
        "phpBB/includes/acp/acp_permission_roles.php",
        "phpBB/ucp.php"
      ]
    },
    {
      "description": "Remaining ACP configuration and extension/style/language/storage/profile/search administration",
      "paths": [
        "phpBB/includes/acp/",
        "phpBB/phpbb/extension/",
        "phpBB/phpbb/search/"
      ]
    },
    {
      "description": "Pruning, maintenance, full delivery/retry and remaining notification types/destinations",
      "paths": [
        "phpBB/phpbb/cron/",
        "phpBB/includes/functions_messenger.php",
        "phpBB/phpbb/notification/"
      ]
    },
    {
      "description": "General session management, orphan administration and complete Held-copy lifecycle",
      "paths": [
        "phpBB/phpbb/session.php",
        "phpBB/includes/acp/acp_attachments.php",
        "phpBB/includes/functions_privmsgs.php"
      ]
    }
  ],
  "limitations": [
    {
      "description": "Core event extension hooks and selected authentication/search/delivery providers can replace or alter the inspected branches",
      "paths": [
        "phpBB/posting.php",
        "phpBB/includes/functions_posting.php",
        "phpBB/includes/functions_privmsgs.php",
        "phpBB/phpbb/auth/",
        "phpBB/phpbb/search/",
        "phpBB/phpbb/notification/"
      ]
    }
  ]
}
---

# Coverage
