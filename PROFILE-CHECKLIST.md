# Profile checklist

For Caleb. GitHub renders `README.md` on the profile and ignores this file, so none of it shows on the profile card. These are account settings and a follow-up repo. This pull request does not change them. Delete this file after the boxes are checked.

## Settings to change

- [ ] **Company → `PEAK`**
  - [github.com/settings/profile](https://github.com/settings/profile) → Public profile → Company.
  - Replace the current value with `PEAK` in all caps. No `@`, and no URL in this field.

- [ ] **Website → `https://calebniednagel.com`**
  - Same page → URL (the website field). It currently points at LinkedIn.
  - Set `https://calebniednagel.com`. LinkedIn stays in the profile README.

- [ ] **Turn on "Include private contributions on my profile"**
  - scottie and SNOVO are private, so the contribution graph stays quiet until this is on. Visitors see counts only. They do not see repo names or code.
  - Profile photo → **Your profile** → above the contribution calendar, **Contribution settings** → **Private contributions**. Docs: [Manage visibility settings for private contributions](https://docs.github.com/en/account-and-profile/how-tos/contribution-settings/manage-visibility-settings-for-private-contributions-and-achievements).
  - If that menu is not there, use the older checkbox on [Public profile](https://github.com/settings/profile): Contributions & activity → **Include private contributions on my profile** → Update preferences.
  - If the graph still looks empty, two GitHub rules are the usual cause: the git author email has to be added to this GitHub account, and the commits have to be on the repository's default branch (or `gh-pages`).

- [ ] **Mark available for hire**
  - The hiring flag is unset today.
  - Profile photo → **Settings** → **Jobs Profile** → **Available for hire** → **Save jobs profile**. Docs: [Set your hiring status](https://docs.github.com/en/account-and-profile/how-tos/account-settings/set-your-hiring-status).

- [ ] **Pin agent-fleet**
  - Profile photo → **Your profile** → **Customize your pins** → select [agent-fleet](https://github.com/clebidk/agent-fleet) → **Save pins**. You can pin six items.
  - Pin this public repo. A private pin is visible to people with access, not to a hiring manager who lacks it, so scottie and SNOVO stay in the README. Leave a second slot for the package below. Do not pin `clebidk/clebidk` in place of agent-fleet.

- [ ] **Bio, under 160 characters** (119 in the suggestion below)

  Replace the current bio with:

  > Chief AI Officer at PEAK. I deploy AI agents into a live DTC business, with a person on every send, spend, and publish.

  Paste it into Public profile → Bio on [github.com/settings/profile](https://github.com/settings/profile).

## First public repo a hiring manager can run

agent-fleet is a write-up. The profile has two public repos, and neither is something a stranger can clone and run. The next public repo should be.

**Suggestion:** `approval-gate`, a small open-source Python package with an approval gate and a claims gate. Same ideas already described in agent-fleet and scottie. No company data.

Scope:

- Runtime is the Python standard library. Tests use pytest.
- Classify an action as `ship`, `gate`, or `never`, the three classes in the agent-fleet write-up.
- A gated action needs an explicit yes and one pre-act line: what is about to happen, why, and what should be true after.
- Never-class actions cannot be approved through the gate: payments, refunds, payroll, deploys, permission changes, bulk exports.
- At most one pending gated ask. Further gated actions wait in a queue.
- Claims gate: given draft sentences and a list of sourced claims, block any sentence that has no source.
- pytest covers each class, a blocked never-action, a second pending ask, and an unsourced sentence.
- `demo.py` uses fake copy. No PEAK prompts, customer text, or real claims.
- MIT license and `pyproject.toml`. A clean clone runs `pytest`, then `python demo.py`, with no accounts and no keys.

When that repo is public and the tests pass, pin it next to agent-fleet.
