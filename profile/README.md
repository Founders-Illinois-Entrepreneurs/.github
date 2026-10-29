# Founders · Illinois Entrepreneurs

The entrepreneurship club at the University of Illinois Urbana-Champaign. Everything the club runs on the web lives here, so it stays with the club when exec members graduate.

| Repo | What it is | Live at | Hosting |
| --- | --- | --- | --- |
| [founders-website](https://github.com/Founders-Illinois-Entrepreneurs/founders-website) | The main club website | [foundersillinois.org](https://foundersillinois.org) | GitHub Pages |
| [events](https://github.com/Founders-Illinois-Entrepreneurs/events) | Live tools for club events | [events.foundersillinois.org](https://events.foundersillinois.org) | Vercel |

## How this org works

**One repo per site, named after its subdomain** (`events` is events.foundersillinois.org). An event is not a new site: it's created from an existing tool's admin page.

**Who can do what:**

| Role | Who | Can |
| --- | --- | --- |
| Owner | At least two exec members | Everything: org settings, inviting people, creating repos, emergency fixes straight to `main` |
| `exec` team | The current exec team | Approve pull requests in every repo, and merge them without waiting for a review |
| `<repo>-maintainers` team (e.g. `events-maintainers`) | The people who know that site's code | The same, in their repo only |
| Member | Anyone contributing | Push branches and open pull requests in every repo |
| Subteam teams: `events`, `exploration`, `community`, `r&d` | Each club subteam's members | Nothing extra: they group people, so a whole subteam can be mentioned (`@Founders-Illinois-Entrepreneurs/r-d`) |

Each repo's `.github/CODEOWNERS` names its approvers: its own maintainers team plus `exec`. Only their approvals count, because each repo requires a review from a code owner.

**How a change gets live:**
1. Push a branch and open a pull request into `main`.
2. Automatic checks (tests, lint, build) must pass, and someone from that repo's maintainers team or `exec` must approve. Team members can also merge their own pull requests without waiting for a review, but not push straight to `main`.
3. Merge. The site deploys on its own within a few minutes.

**Org settings, and why:**
- Only owners create, delete or transfer repos, so each repo maps to a real site and nothing disappears by accident.
- Members can't change a repo's visibility. Every repo stays public, which keeps branch rules and hosting free.
- Only owners can give someone outside the org access to a repo (members don't have admin access to any repo). People join through the org instead.
- New repos start with secret scanning and push protection on (a push containing a password or key is blocked), plus Dependabot security alerts.

## Contributing

Ask an exec member to invite you to the org. Then:

- **Read the repo's README first.** It explains how to run the site locally and how it's deployed.
- **Never commit secrets or personal data.** Every repo here is public. Passwords and database URLs go in the hosting settings (Vercel environment variables). Member lists, emails and phone numbers stay out of git.
- **Never develop against a live database.** Each repo's README explains how to get your own copy.
- **Add yourself to the Credits section** of the README in your pull request, with a link to your GitHub profile.

## Running the org

For exec members and owners.

**Common tasks:**

| To… | Do this |
| --- | --- |
| Add a contributor | Org → **People** → **Invite member** (role: Member) |
| Let someone approve pull requests for one repo | Org → **Teams** → `<repo>-maintainers` → **Add a member** |
| Add an exec member | Org → **Teams** → `exec` → **Add a member** (and make them an owner if they'll run the org) |
| Put someone in their club subteam | Org → **Teams** → `events`, `exploration`, `community` or `r&d` → **Add a member** |
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
