# Founders · Illinois Entrepreneurs

The entrepreneurship club at the University of Illinois Urbana-Champaign. Everything the club runs on the web lives here, so it stays with the club when exec members graduate.

| Repo | What it is | Live at | Hosting |
| --- | --- | --- | --- |
| [founders-website](https://github.com/Founders-Illinois-Entrepreneurs/founders-website) | The main club website | [foundersillinois.org](https://foundersillinois.org) | GitHub Pages |
| [events](https://github.com/Founders-Illinois-Entrepreneurs/events) | Live event tools (R&D pitch evaluation game) | [events.foundersillinois.org](https://events.foundersillinois.org) | Vercel |

## How this org works

**One repo per site, named after its subdomain** (`events` is events.foundersillinois.org). An event is not a new site: it's created from an existing tool's admin page.

**Who can do what:**

| Role | Who | Can |
| --- | --- | --- |
| Owner | At least two exec members | Everything: org settings, inviting people, creating repos, emergency fixes straight to `main` |
| `exec` team | The current exec team | Approve pull requests in every repo, and merge them without waiting for a review |
| `<repo>-maintainers` team (e.g. `events-maintainers`) | The people who know that site's code | The same, in their repo only |
| Member | Anyone contributing | Push branches and open pull requests in every repo |

Each repo's `.github/CODEOWNERS` names its approvers: its own maintainers team plus `exec`. Only their approvals count, because each repo requires a review from a code owner.

**How a change gets live:**
1. Push a branch and open a pull request into `main`.
2. Automatic checks (tests, lint, build) must pass, and someone from that repo's maintainers team or `exec` must approve. Team members can also merge their own pull requests without waiting for a review, but not push straight to `main`.
3. Merge. The site deploys on its own within a few minutes.

**Org settings, and why:**
- Only owners create, delete or transfer repos, so each repo maps to a real site and nothing disappears by accident.
- Members can't change a repo's visibility. Every repo stays public, which keeps branch rules and hosting free.
- Members can't invite outside collaborators. People join through the org instead.
- New repos start with secret scanning and push protection on (a push containing a password or key is blocked), plus Dependabot security alerts.

## Contributing

Ask an exec member to invite you to the org. Then:

- **Read the repo's README first.** It explains how to run the site locally and how it's deployed.
- **Never commit secrets or personal data.** Every repo here is public. Passwords and database URLs go in the hosting settings (Vercel environment variables). Member lists, emails and phone numbers stay out of git.
- **Never develop against a live database.** Each repo's README explains how to get your own copy.
- **Add yourself to the Credits section** of the README in your pull request, with a link to your GitHub profile.

## For exec: running the org

Account logins, who holds them, renewal dates and contacts are in the private **Tech handover** doc in the club's Google Drive, shared with the exec team. Never put those details here: this page is public.

**How it's owned:**
- **Code:** this GitHub org, with at least two exec members as owners at all times.
- **Hosting and domain** (Vercel with its Neon database, and the Namecheap domain) are signed in with the club's shared team account, never anyone's personal email. At least two exec members hold its password and backup codes.
- **Secrets** live only in Vercel's environment variables, never in a repo.
- **Recurring cost:** only the `foundersillinois.org` domain renewal.

**Common tasks:**

| To… | Do this |
| --- | --- |
| Add a contributor | Org → **People** → **Invite member** (role: Member) |
| Let someone approve pull requests for one repo | Org → **Teams** → `<repo>-maintainers` → **Add a member** |
| Add an exec member | Org → **Teams** → `exec` → **Add a member** (and make them an owner if they'll run the org) |
| Remove someone | Org → **People** → their name → **Remove from organization** |
| Make an exec member an owner | Org → **People** → their name → **Change role** → Owner |
| Change how many approvals a repo needs | Repo → **Settings** → **Rules** → **Rulesets** → `Protect main` → **Required approvals** |

**Adding a new site:**
1. Create the repo in this org (public), named after its subdomain.
2. Org → **Teams** → **New team** `<repo>-maintainers`. Then repo → **Settings** → **Collaborators and teams**: give it and `exec` **Write** access.
3. Add `.github/CODEOWNERS` containing `* @Founders-Illinois-Entrepreneurs/<repo>-maintainers @Founders-Illinois-Entrepreneurs/exec`.
4. Copy the branch rules from `events` (Settings → Rules → Rulesets → `Protect main` → export, then import in the new repo).
5. Host it in the club's Vercel account (apps with a server or database) or on GitHub Pages (static sites). Never a personal account.
6. Add a CNAME record for the subdomain in Namecheap DNS.
7. Add a row to the table at the top of this page (`profile/README.md` in the [`.github`](https://github.com/Founders-Illinois-Entrepreneurs/.github) repo).

**When the exec team changes:** follow the **Each semester** checklist in the Tech handover doc. In short:
- Hand over ownership, the team account password and backup codes.
- Update the `exec` team and each repo's maintainers team.
- Change the events organizer password.
- Check the domain renewal.
