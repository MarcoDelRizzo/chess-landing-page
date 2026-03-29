# Chess Mentor Landing Page

Astro landing page for GitHub Pages with a MailerLite-ready waitlist section.

## Project structure

- `src/pages/index.astro`: landing page content and styling
- `src/layouts/BaseLayout.astro`: shared document layout
- `public/CNAME`: custom domain for GitHub Pages
- `.github/workflows/deploy.yml`: automatic GitHub Pages deployment

## Local development

Install dependencies:

```bash
npm install
```

Run the dev server:

```bash
npm run dev
```

Build for production:

```bash
npm run build
```

Preview the production build:

```bash
npm run preview
```

## Make the waitlist live with MailerLite

1. Create an **Embedded form** in MailerLite.
2. Copy the **universal JavaScript snippet** and paste it into `src/layouts/BaseLayout.astro` inside `<head>`.
3. Copy the **form snippet** for that embedded form and replace the placeholder content inside the `mailerlite-form-slot` section in `src/pages/index.astro`.

Official MailerLite guide:

- [How to add a form to your website](https://www.mailerlite.com/help/how-to-add-a-form-to-your-website)

## Deploy to GitHub Pages

1. Push the repo to GitHub.
2. Open the repo on GitHub and go to `Settings -> Pages`.
3. Under **Build and deployment**, set **Source** to **GitHub Actions**.
4. Push to `main` and GitHub will run `.github/workflows/deploy.yml`.
5. Wait for the Pages deployment to finish. GitHub will then show the site URL in the Pages settings.

## Connect `chess.delrizzo.dev` with Porkbun

This project already includes `public/CNAME` with `chess.delrizzo.dev`, which helps GitHub Pages keep the custom domain attached.

1. In GitHub, open `Settings -> Pages`.
2. Confirm the custom domain is `chess.delrizzo.dev`.
3. In Porkbun DNS, add this record:

```txt
Type: CNAME
Host: chess
Answer: <your-github-username>.github.io
TTL: 600 or default
```

4. Save the DNS record and wait for propagation.
5. Return to GitHub Pages and enable **Enforce HTTPS** after GitHub finishes validating the domain.

Recommended GitHub docs:

- [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
- [Verifying your custom domain for GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages)

## Next best step

Create the embedded form in MailerLite, then paste the snippets into the two Astro files above and the waitlist will be live.
