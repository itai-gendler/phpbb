---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account"
    },
    {
      "type": "entity",
      "id": "board-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/user.php#setup"
    }
  ]
}
---

# Configured credential age carries the account holder to account settings

For an eligible registered user outside the User Control Panel, with u_chgpasswd and no administrative exemption, user setup compares Credential changed at with the configured Forced password age and redirects an expired account to account registration details. The attempted topic reading is intercepted before content display; successful password replacement updates the verifier and Credential changed at. The rule does not invent a user-controlled expiry state.
