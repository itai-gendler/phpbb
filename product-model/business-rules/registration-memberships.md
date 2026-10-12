---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account"
    },
    {
      "type": "entity",
      "id": "group-membership"
    }
  ],
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

# Registration and threshold departure maintain the applicable memberships

Registration creates the applicable registered-user or COPPA group membership and default group, and also the configured newly registered membership when that policy applies. Activation changes account eligibility without erasing those memberships. On the post-count threshold path, departure from the newly registered group removes that actual membership, updates New member status and adjusts a default-group dependency when required. 
