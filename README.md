# Aerolex AI Development Test

## Project Overview

A personal, non-commercial learning project recreating the Aerolex website with authorized design assets.

**Astro + Tailwind CSS** build the frontend from JSON content and images. **GitHub** stores the source, and **Vercel** builds and hosts it. **Directus** is a separate local CMS experiment; it is not connected to the deployed frontend. Pages CMS is a configured alternative for editing repository content.

## Local Development

Requirements: Git, Node.js **22.23.4** (see `.nvmrc`), npm, and Python 3 for route checks. If using nvm, run `nvm install` and `nvm use` after cloning.

```sh
git clone https://github.com/Levani1111/aerolex-ai-development-test.git
cd aerolex-ai-development-test
npm ci
npm run dev -- --background
```

Open [localhost:4321](http://localhost:4321), or the URL printed by Astro if the port is occupied. Stop with `npm run astro -- dev stop`.

Before pushing changes:

```sh
npm run check
npm run build
npm run test:routes
```

## CMS Setup & Login

**Directus — existing local installation only**

This repository does not include Directus, its database, uploads, or credentials. On the existing development Mac, start the separately provisioned instance with:

```sh
npm --prefix /Users/levanipapashvili/Projects/aerolex-ai-development-test run cms:start
```

This command requires that existing local installation; it will not work from a fresh clone alone. A new developer needs a separately provisioned Directus instance or a secure handover from the maintainer.

- Login: [127.0.0.1:8055/admin](http://127.0.0.1:8055/admin)
- Existing test login email: `editor@example.com`
- Password: obtain privately from the maintainer or the existing installation's Git-ignored `local-cms/LOGIN.txt`. Never commit this file.
- In Directus, open a page, course, or article collection, edit fields, select/upload images, and save.

The separate installation's sync/watch tools export to its own local checkout, **not this personal repository**. Saved CMS changes do not update Vercel. Publishing here requires reviewing and copying the intended JSON/images into this repository, validating, committing, and pushing.

**Pages CMS alternative**

`.pages.yml` configures pages, navigation, footer, courses, posts, and image uploads. Sign in at [Pages CMS](https://app.pagescms.org) with GitHub, authorize this personal repository, and select `main`. Images go into `public/images`. Saves to `main` would trigger Vercel; repository authorization and an end-to-end editing test are still unverified. See the [Pages CMS documentation](https://pagescms.org/docs/).

## Deployment

The personal GitHub repository is connected to Vercel. Pushes to `main` automatically trigger a production build; GitHub Actions also validates the project.

Initial setup is already complete. To recreate it, import this repository into Vercel and use:

- Framework: **Astro**; root: repository root; Node: **22.x**
- Install: `npm ci`; build: `npm run build`; output: `dist`
- No frontend secrets required. Use Hobby only for eligible personal, non-commercial use.

For a manual rebuild, open the project → **Deployments** → select a deployment → **… → Redeploy**. See [Vercel's deployment guide](https://vercel.com/docs/deployments/managing-deployments).

Live website: [aerolex-ai-development-test.vercel.app](https://aerolex-ai-development-test.vercel.app/).

## Project Structure

| Path | Purpose |
| --- | --- |
| `src/pages/` | Pages and course/article routes |
| `src/components/`, `src/layouts/` | Reusable UI and layouts |
| `src/content/` | Editable JSON, including courses and posts |
| `public/images/`, `public/fonts/` | Website assets |
| `.pages.yml` | Pages CMS fields and uploads |
| `vercel.json` | Static build settings |
| `scripts/`, `.github/workflows/ci.yml` | Validation and CI checks |

## Current Limitations

- Directus is local only; no online Directus login or publishing webhook is configured.
- Pages CMS online editing has not been verified for this repository.
- The contact form validates inputs but does not send emails.
- Some design content is sample/repeated text; legal pages are placeholders.
- Asset permission covers this learning project, not general redistribution. Fonts retain their OFL licence.

## Useful Links

- [Live website](https://aerolex-ai-development-test.vercel.app/)
- [Personal GitHub repository](https://github.com/Levani1111/aerolex-ai-development-test)
- [Vercel dashboard](https://vercel.com/cs-ddd5/aerolex-ai-development-test)
- [Local Directus login](http://127.0.0.1:8055/admin) — available only on the machine running it
- [Pages CMS login](https://app.pagescms.org)
