---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "forum"
    },
    {
      "type": "entity",
      "id": "topic"
    },
    {
      "type": "entity",
      "id": "post"
    },
    {
      "type": "entity",
      "id": "attachment"
    },
    {
      "type": "entity",
      "id": "post-report"
    },
    {
      "type": "entity",
      "id": "bookmark"
    },
    {
      "type": "entity",
      "id": "topic-subscription"
    },
    {
      "type": "entity",
      "id": "forum-subscription"
    },
    {
      "type": "entity",
      "id": "private-message"
    },
    {
      "type": "entity",
      "id": "message-copy"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_admin.php#delete_posts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_admin.php#delete_topics"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php#delete_forum"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#delete_pm"
    }
  ]
}
---

# Content removal preserves dependencies and movement choices

Mapped permanent post removal removes dependent attachments and reports and synchronizes the containing topic/forum; when the removed post is the last contribution, its topic is removed. Soft deletion preserves stored content with Deleted visibility and deletion information. Forum deletion honors the selected valid content/subforum deletion or movement choices; it must not claim universal cascading deletion when content is moved. Attachment removal during parsing is immediate, including attached-file removal and derived parent flags, and is not rolled back by a later refused parent form.
