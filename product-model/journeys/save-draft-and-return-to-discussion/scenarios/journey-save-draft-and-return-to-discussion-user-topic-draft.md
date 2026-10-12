---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User saves a nonempty subject and content as a draft.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      },
      "capability": "save-forum-draft"
    },
    {
      "text": "A Saved draft keeps the registered identity and destination; completion schedules the posting area or discussion without publication.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-draft",
          "effect": "creates",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Saved at",
            "Forum",
            "Topic"
          ],
          "to": "Saved"
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      },
      "capability": "save-forum-draft"
    },
    {
      "text": "The Product carries User through the completion destination into browse discussion",
      "kind": "product",
      "actor": "user",
      "capability": "save-forum-draft",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The User opens a posting area.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::forum"
        }
      },
      "capability": "browse-topics"
    },
    {
      "text": "The list displays disclosed discussions with subjects, contribution summaries and paging.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Rules",
            "Topic counts",
            "Last contribution"
          ]
        },
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Created at",
            "Approved count",
            "Last contribution"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::forum"
        }
      },
      "capability": "browse-topics"
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
      "target": "phpBB/includes/functions_posting.php#submit_post"
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
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#is_visible"
    }
  ]
}
---

# Save draft and return to discussion — user topic draft

## Trigger

Save the current forum draft and reach the discussion destination.

## Outcome

The contributor reaches the scheduled forum list or selected topic while the draft remains Saved.
