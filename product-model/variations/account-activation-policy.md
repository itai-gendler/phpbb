---
{
  "kind": "configuration",
  "of": "business-rule",
  "settings": [
    {
      "entity": "board-settings",
      "fact": "Registration mode"
    }
  ],
  "takesEffect": "When an activation link is followed. Activation reads the current Registration mode, so a change applies to the next attempt.",
  "stability": "Accounts already Inactive keep their Inactivity reason and key. A mode change changes who may activate those pending accounts; emails and administrator alerts already sent at registration or email change stay as sent.",
  "alternatives": [
    {
      "id": "account-activation-by-account-holder",
      "selectedWhen": "Registration mode is By user (email verification). Any mode other than By admin selects it too, for accounts that are still Inactive (such as COPPA registrations under No activation)."
    },
    {
      "id": "account-activation-by-administrator",
      "selectedWhen": "Registration mode is By admin."
    }
  ]
}
---

# Account activation policy

Boards choose whether the account holder or an administrator activates new and changed accounts; both policies are supported. Under No activation (immediate access) registration creates the account Active, so there is nothing to activate. Disabling registration is an on/off condition on account registration, not a third policy.
