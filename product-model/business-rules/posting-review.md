---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "post"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/posting.php"
    }
  ]
}
---

# Intervening contributions interrupt enabled posting review

When Forum Post review is enabled and a supplied nonzero last-post position differs from the current position, reply/quote submission is interrupted and refreshed; topic_review returning content determines whether the review panel is displayed. Editing is likewise interrupted when a nonempty original content checksum changed and the submitted content differs from the newer content, or when the corresponding nonempty subject-checksum comparison changes. The newer-version panel is displayed when topic_review returns content. Matching the already-kept newer content does not trigger the content-checksum branch. The contributor’s proposed input remains available; the interrupted submission does not overwrite the contribution.
