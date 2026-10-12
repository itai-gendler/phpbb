---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/log/log.php#add"
    }
  ]
}
---

# Log entry

An actor-visible record of an operation.

## Information kept

- **Actor** — Who initiated the recorded operation.
- **Operation** — The recorded operation and event meaning.
- **Recorded at** — When the operation was recorded.
- **IP** — The recorded operation’s address.
- **Category** — The administration, moderation, user or critical log category.
- **Subject** — The recorded operation’s affected subject.
- **Event information** — The event-specific arguments kept for log presentation.
