# Testing Checklist — Devices GitHub Automation

A running list of things to test with the working group. Check items off as they're verified; add new ones as we build more. Each item notes **who** should do it, since some tests require a non-owner or a brand-new user to be meaningful.

> **Legend:** ⬜ not tested · ✅ verified working · ❌ found a problem (note it)

---

## 1. Repository creation automation

- ⬜ **Co-chair can create a repo.** A `dev-co-chairs` member opens *New Repository Request* → repo is created from the template. _(who: a co-chair, not you)_
- ⬜ **Non-co-chair is blocked.** Someone NOT in `dev-co-chairs` opens the same request → it's declined with a comment and the issue is closed, no repo created. _(who: a regular member)_
- ⬜ **Per-repo teams are created.** After creation, `{name} writer` and `{name} maintainer` teams exist as child teams of `devices-domain`. _(who: anyone)_
- ⬜ **Team roles are correct.** The new repo shows `dev-co-chairs` = Admin, `{name} maintainer` = Maintain, `{name} writer` = Write. _(who: anyone with repo access)_
- ⬜ **Result comment is accurate.** The issue's closing comment lists the repo and all three teams with the right roles. _(who: anyone)_

## 2. Adding people to teams automation

- ⬜ **Co-chair can add an existing org member.** Open *Add People to a Team*, list a username already in the IHE org → they're added immediately. _(who: a co-chair)_
- ⬜ **★ Brand-new person gets an org invite.** List someone who is NOT yet in the IHE org → they receive an email invitation, and once they accept they land on the team. **This is the key assumption — confirm it actually works.** _(who: a co-chair + a volunteer who isn't in the org yet)_
- ⬜ **Email address works.** List an email address (not a username) → an org invitation is sent. _(who: a co-chair)_
- ⬜ **Team maintainer (non-co-chair) can add to their own team.** A maintainer of `WIA writer` adds someone to `WIA writer` → succeeds. _(who: a team maintainer who is not a co-chair)_
- ⬜ **Unauthorized person is blocked.** Someone who is neither a co-chair nor a maintainer of the target team → request declined. _(who: a regular member)_
- ⬜ **Wrong team name is rejected helpfully.** Type a team that doesn't exist → declined with a comment listing the valid teams. _(who: a co-chair)_
- ⬜ **Bad username is reported.** Include a misspelled/nonexistent username among good ones → the good ones still succeed and the bad one is flagged in the result table. _(who: a co-chair)_
- ⬜ **Capitalization / spacing is forgiving.** Type `wia writer` or `WIA Writer` for a team named `WIA writer` → still resolves. _(who: a co-chair)_

## 3. Change Proposal (CP) workflow

- ⬜ **CP folders exist in a new repo.** A repo made from the template has `CP/` and `CP/Approved/`. _(who: anyone)_
- ⬜ **Create-a-CP flow is clear.** Walk a lead author through: branch → add CP file → merge to main → work on CP branch → PR to ballot. Does the documented flow make sense to them? _(who: a lead author)_
- ⬜ **Approved CP move works.** Move a test CP file from `CP/` to `CP/Approved/` via PR. _(who: a lead author)_

## 4. Build / CI (already validated, re-confirm on a real repo)

- ⬜ **Build runs on push.** Pushing to `main` of a new supplement repo produces HTML + PDF artifacts. _(who: a contributor)_
- ⬜ **Shared theme is applied.** The built output picks up the shared IHE theme from DEV.tooling. _(who: anyone reviewing output)_

## 5. Documentation review

- ⬜ **Playbooks match reality.** Have each role (org admin, domain lead, contributor, reviewer) read their playbook and confirm the steps match what they actually see in GitHub. _(who: one person per role)_
- ⬜ **Team reference is clear.** The Teams reference correctly explains parent/child teams, making managers, and the org-invite catch. _(who: a co-chair)_

---

## Open questions to raise in the meeting

- Public vs. private repos — still undecided.
- License for document content — still deferred.
- Should approved CPs ever be archived, and how? (We dropped the `Archive/` folders for now.)
- The existing teams have mixed display-name styles (e.g. `SDPi writer` vs `dev-co-chairs`) — do we want to standardize?
