---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_user.php#user_add"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/session.php"
    }
  ]
}
---

# Group membership

The account’s pending or established group membership, including default and leader status.

## Information kept

- **Account** — The affected registered identity.
- **Group** — The selected runtime group.
- **Pending** — Whether membership awaits acceptance.
- **Leader** — Whether this membership holds group leadership.
- **Default** — Whether this is the account’s default group membership.

## States

### Pending

Membership awaits acceptance.

### Member

Membership is established.
