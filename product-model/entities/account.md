---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_profile.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_user.php#user_add"
    }
  ],
  "relations": [
    {
      "entity": "forum-draft",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "bookmark",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "topic-subscription",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "forum-subscription",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "message-copy",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "notification",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "group-membership",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "user-permissions",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "topic",
      "verb": "authors",
      "cardinality": "one-to-many"
    },
    {
      "entity": "post",
      "verb": "authors",
      "cardinality": "one-to-many"
    },
    {
      "entity": "private-message",
      "verb": "authors",
      "cardinality": "one-to-many"
    },
    {
      "entity": "attachment",
      "verb": "uploads",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Account

The registered identity whose facts remain the same across the person’s forum roles.

## Information kept

- **Username** — The name used for signing in and member/contribution attribution.
- **Email** — The registered contact address used by account processes and governed contact disclosure.
- **Credential** — The password verifier; never disclosed as a stored value.
- **Joined at** — When registration created the identity.
- **Inactivity reason** — The reason for inactivity, including registration, email change, forced reactivation and manual inactivity.
- **Activation proof** — The kept activation key used to authenticate the activation link; never disclosed as a verifier.
- **Activation expiry** — The kept activation timing value; the activation handler does not enforce equivalent reset-token expiry.
- **Reset proof** — The current password-reset verifier; replacement and expiration cleanup maintain it.
- **Reset expiry** — The reset token’s expiry time, enforced during replacement.
- **Credential changed at** — The last password-change time used by forced-change policy.
- **New member status** — Whether newly registered-member treatment still applies.
- **Profile values** — The configured profile/contact field values kept for this person.
- **Birthday** — The kept birth date from which the configured displayed age is derived.
- **Preferred language** — The personal language choice used for the interface and account messages.
- **Timezone** — The personal timezone used for date presentation.
- **Date format** — The personal date presentation preference.
- **Style** — The personal style choice subject to the board style policy.
- **Allow private messages** — The receiving preference respected by ordinary senders and the privileged exception.
- **Allow email contact** — The personal preference used when generating member contact disclosure.
- **Allow mass email** — The personal mass-email preference.
- **Online visibility** — The account’s preference for disclosure of its online activity.
- **Online presence** — The tracked online presence exposed only by the applicable disclosure policy.
- **Display options** — Personal display/sorting and contribution-format preferences.
- **Censor preference** — The personal word-censor choice; write authority and board presentation override remain separate.
- **Posting defaults** — Default formatting/signature/notification choices for composing.
- **Notification choices** — The account’s type and method subscription preferences.
- **Post count** — The approved, counted contributions credited to this identity.
- **Last post at** — The latest kept contribution/message posting time consulted by flood control.
- **New message count** — The number of mailbox messages recorded as new for this identity.
- **Unread message count** — The number of mailbox messages recorded as unread for this identity.
- **Last active at** — The kept last activity time with the session-time display fallback.

## States

### Inactive

The identity awaits activation or has an applicable inactivity reason.

### Active

The identity is active.
