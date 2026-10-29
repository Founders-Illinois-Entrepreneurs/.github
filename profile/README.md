# Founders · Illinois Entrepreneurs

The entrepreneurship club at the University of Illinois Urbana-Champaign. Everything the club runs on the web lives here, so it stays with the club when officers graduate. Each site has its own repo, named after its subdomain.

| Repo | What it is | Live at | Hosting |
| --- | --- | --- | --- |
| [founders-website](https://github.com/Founders-Illinois-Entrepreneurs/founders-website) | The main club website | [foundersillinois.org](https://foundersillinois.org) | GitHub Pages |
| [events](https://github.com/Founders-Illinois-Entrepreneurs/events) | Live event tools (R&D pitch evaluation game) | [events.foundersillinois.org](https://events.foundersillinois.org) | Vercel |

## Want to contribute?

Ask an officer to add you to the org. Then branch, open a pull request, and get one approval. Merging to `main` deploys automatically. Each repo's README explains how to run it locally.

## For officers: how the club's tech is owned

- **Code:** in this GitHub org. Keep at least two owners at all times, and remove people when they graduate.
- **Hosting accounts** (Vercel, Neon database) and the **domain** (Namecheap) should all be signed in with the club's shared Google account, not anyone's personal email. The current president and tech lead hold its password and backup codes.
- **Secrets** (database URLs, admin passwords) live only in Vercel's environment variables, never in a repo. All repos here are public.
- **Recurring cost:** only the `foundersillinois.org` domain renewal.
