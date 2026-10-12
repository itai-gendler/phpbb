---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/report/report_handler_post.php"
    }
  ]
}
---

# Post report

A submitted report retaining the reported content’s submission-time snapshot.

## Information kept

- **Reporter** — The submitting identity, including admitted anonymous reporting.
- **Post** — The contribution associated with the report.
- **Reason** — The selected report reason, including Other requiring explanation.
- **Text** — The reporter’s explanatory input.
- **Notify reporter** — The submitted request for applicable resolution dispatch.
- **Reported at** — When the report was submitted.
- **Content snapshot** — The content captured when the report was submitted.
- **Snapshot formatting** — The formatting information needed to display that captured content.

## States

### Open

The report awaits resolution.

### Closed

The report is resolved and its snapshot retained.
