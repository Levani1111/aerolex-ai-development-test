# Aerolex personal learning website

Personal, non-commercial learning and testing copy owned by Levani1111. The project owner confirmed permission to publish the code, design, branding, images and content for this purpose. This does not grant a general licence to third parties. Bundled fonts retain their OFL licence.

## Develop and verify

Use Node 22.x. Run `npm ci`, `npm run dev`, `npm run check`, `npm run build`, and `npm run test:routes`. Static output is `dist`.

## Content

Edit JSON in `src/content`, with images in `public/images`. `.pages.yml` describes Pages CMS fields, including courses and blog posts. Pages CMS requires a separate GitHub authorization; no CMS credentials are needed for the frontend build.

## Vercel

Import Levani1111/aerolex-ai-development-test into the existing free Hobby account for this personal non-commercial project. Framework: Astro; install: `npm ci`; build: `npm run build`; output: `dist`; Node: 22.x. Git integration deploys pushes automatically. No environment secrets are required. No custom production DNS is used.

Directus is separate and remains local in the original project. This repository contains no Directus runtime, databases, uploads, credentials or old Git history. CMS publishing is not connected automatically.

## Demo limitations

The contact form validates inputs but does not send email. Some Figma content repeats or uses sample text; legal pages are placeholders. This is a learning demonstration, not the live Aerolex service.
