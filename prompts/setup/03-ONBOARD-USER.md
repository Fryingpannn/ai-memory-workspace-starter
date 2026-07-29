# Stage 3: Create the Portable User Profile

Run a short, optional questionnaire through the user's current agent. The root
`USER.md` is the portable user profile shared across file-aware harnesses.

## Ask Once

Offer the profile first. Explain that the user may decline or answer only what they are
comfortable sharing. If accepted, ask in one message:

```text
1. What should agents call you?
2. What do you do, and what are your current priorities or areas of work?
3. How do you like agents to work with you—communication style, initiative, and
   anything that should always require your approval?
4. In one sentence, what should this outer workspace help you do or remember over time?
```

Keep the exchange light and conversational. Volunteered facts come first.

If the user declines:

- stop the personal questions immediately;
- if `USER.md` is the new starter default, replace its brackets with `NOT PROVIDED`
  rather than leaving unresolved placeholders;
- record only that onboarding was declined, without guessing why;
- ask only for the workspace-purpose sentence later when Stage 4 needs it.

## External Lookup

Do not perform an external lookup by default.

If the user wants public details confirmed:

1. say exactly what you intend to check;
2. get explicit consent for that lookup;
3. use the user's default browser;
4. never read connected email, calendar, or other accounts without separate consent.

If browser control is unavailable, skip the lookup and ask the user to confirm the fact.

## Store the Profile

- If `USER.md` is the newly scaffolded default, replace only its placeholders with
  confirmed facts and show the result.
- If it existed before setup, preserve it and show proposed targeted additions before
  editing.
- Keep entries compact and high-signal.
- Keep `USER.md` under 100 lines. Consolidate or replace outdated entries instead of
  appending indefinitely; do not silently discard still-current confirmed information.
- Record unknowns as `UNKNOWN`; do not infer personal facts.
- Do not leave bracketed starter placeholders after this stage.
- Do not create a duplicate `wiki/pages/user-profile.md`.

`wiki/index.md` links to the root profile. Future agents discover it through
`AGENTS.md`, regardless of harness.

Return the confirmed workspace purpose and profile path to the setup manager.
