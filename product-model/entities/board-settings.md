---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_board.php"
    }
  ],
  "singleton": true
}
---

# Board settings

The board’s single kept configuration, consulted by the core paths.

## Information kept

- **Registration mode** — The shipped immediate-access, user/email verification, administrator activation or disable-registration choice.
- **New member policy** — The configured new-member group/default treatment and counted-post departure threshold.
- **Name rules** — The configured username length/character/validation requirements.
- **Password rules** — The configured password length/complexity requirements.
- **Forced password age** — The configured age that triggers the eligible account-change continuation.
- **Name change enabled** — Whether the board enables the ordinary username-change field.
- **Email reuse enabled** — The configured duplicate-account-email allowance used in validation.
- **Registration challenge** — The configured registration CAPTCHA choice and related validation.
- **Login attempt limit** — The failed-login limit used to require a challenge.
- **Registration attempt limit** — The limit consulted while validating registration challenge attempts.
- **COPPA settings** — The configured COPPA age/agreement/contact and registration treatment.
- **Email enabled** — Whether email is enabled for the activation/reset/contact paths.
- **Password reset enabled** — Whether the reset process is offered.
- **Own pending visibility** — Whether a signed-in author may see their own Unapproved/Reapproval required contributions.
- **Search settings** — Search enablement, validation/timing limits and forum/result options.
- **Search backend** — The configured provider loaded by searches and contribution indexing.
- **Posting limits** — The configured character/link/smiley/quote and content-validation bounds.
- **Posting format settings** — The board BBCode/smiley/link/signature and allowed-content settings.
- **Edit window** — The configured ordinary post-edit interval; zero disables its time bound.
- **Deletion window** — The configured ordinary post-delete interval; zero disables its time bound.
- **Flood interval** — The interval compared with the applicable most recent posting time.
- **Post presentation settings** — The configured discussion paging/hot-topic and presentation values.
- **Bump settings** — The configured bump interval and relevant controls.
- **Poll limit** — The board maximum poll options consulted by posting validation.
- **Mention settings** — The configured mention handling limits/options.
- **Quick reply enabled** — Whether the board offers its quick-reply control.
- **Guest challenge** — Whether guest posting uses its configured challenge.
- **Topic notifications enabled** — Whether topic-watch creation is offered on the paths.
- **Forum notifications enabled** — Whether forum-watch creation is offered.
- **Bookmarks enabled** — Whether bookmark creation/list access is offered.
- **Censor override enabled** — Whether personal censor override is used in presentation.
- **Attachment settings** — Per-use enablement, file/extension/media/count/size/quota/storage options and secure-download linkage/site-list configuration.
- **Private-message settings** — Enablement, forwarding/mass addressing, recipient limits, edit interval and relevant formatting/file choices.
- **Board notifications enabled** — Whether the board notification list/method is enabled.
- **Notification methods** — The configured available notification method providers.
- **Profile disclosure** — The birthday, activity, contact and related disclosure configuration.
- **Style policy** — The board default style and whether personal style override is honored.
- **Board availability** — Disabled-board audience and configured availability checks, with the implemented administrative/moderator and login exceptions.
- **Load limit** — The configured board-load gate, with the implemented audience exceptions.
