# Founders · Illinois Entrepreneurs

The entrepreneurship club at the University of Illinois Urbana-Champaign. Everything the club runs on the web lives here, so it stays with the club when officers graduate. Each site has its own repo, named after its subdomain.

| Repo | What it is | Live at | Hosting |
| --- | --- | --- | --- |
| [founders-website](https://github.com/Founders-Illinois-Entrepreneurs/founders-website) | The main club website | [foundersillinois.org](https://foundersillinois.org) | GitHub Pages |
| [events](https://github.com/Founders-Illinois-Entrepreneurs/events) | Live event tools (R&D pitch evaluation game) | [events.foundersillinois.org](https://events.foundersillinois.org) | Vercel |

## Want to contribute?

Ask an officer to add you to the org. Then:

- **Work in a branch and open a pull request into `main`.** One approval and passing checks are needed to merge. Merging deploys automatically.
- **Never commit secrets or personal data.** Every repo here is public. Passwords and database URLs go in the hosting settings (Vercel environment variables). Member lists, emails and phone numbers stay out of git.
- **Never develop against a live database.** Each repo's README explains how to get your own copy.
- **Add yourself to the Credits section** of the README in your pull request. A LinkedIn link is optional.
- **Each repo's README** explains how to run it and how it's deployed.

## Adding a new site

Each site gets its own repo, named after its subdomain (e.g. `vote` for vote.foundersillinois.org). An event is not a new site: create it from an existing tool's admin page.

1. Create the repo in this org (public).
2. Copy the `main` branch rules from `events`: Settings → Rules → Rulesets.
3. Host it in the club's Vercel account (for apps with a server or database) or on GitHub Pages (for static sites). Never a personal account.
4. Add a CNAME record for the subdomain in Namecheap DNS.
5. Add a row to the table above (edit `profile/README.md` in the [`.github`](https://github.com/Founders-Illinois-Entrepreneurs/.github) repo).

## For officers: ownership and handover

Account logins, who holds them, renewal dates and contacts are in the private **Tech handover** doc in the club's Google Drive. Ask the president for access. Never put those details here: this page is public.

How it's owned:
- **Code:** this GitHub org. Keep at least two owners at all times.
- **Accounts** (Vercel with its Neon database, and the Namecheap domain) are signed in with the club's shared team account, never anyone's personal email. The president and the tech lead hold its password and two-factor backup codes.
- **Secrets** live only in Vercel's environment variables, never in a repo.
- **Recurring cost:** only the `foundersillinois.org` domain renewal (Namecheap). Keep auto-renew on and check the payment card each year.

When officers change (each semester):
1. Make the incoming tech lead an org **owner**. Remove anyone who has left the club or graduated.
2. Change the shared account's password, and hand it and the backup codes to the incoming president and tech lead.
3. Rotate secrets that departing officers knew, like the events organizer password (`ADMIN_PASSWORD` in Vercel, then redeploy).
4. Check that the domain renewal date and payment card are still valid.
5. Walk the new tech lead through this page and each repo's README.
