# Funngro two-page website redesign

An independent, static HTML/CSS/JavaScript redesign concept for a website-development evaluation. It contains two separate pages:

- `index.html` — Company
- `teen.html` — For teens / Teenlancer journey

This is not an official Funngro website and is not affiliated with Wishbanc Technologies Private Limited. It uses original SVG illustrations and a green-forward visual direction; it does not reproduce Funngro's logo or claim official brand approval.

## 1. Research notes and content decisions

Research was based on the current public Funngro website, reviewed on **25 November 2026**:

- [Funngro home page](https://www.funngro.com/) — current positioning and the broad company-to-youth platform proposition.
- [About Funngro](https://www.funngro.com/about) — states that Funngro started in 2022 and describes the company's public story, including its Shark Tank India Season 2 appearance.
- [Teen page](https://www.funngro.com/teen) — describes the Teenlancer journey and names categories including brand promotion, sampling, referrals, surveys, influencer briefs and content tasks. Its page copy describes choosing a campaign, completing the task, uploading proof and waiting for verification.
- [FAQ](https://www.funngro.com/faq) — reference for current earner and brand questions.
- [Terms & Conditions](https://www.funngro.com/terms-and-conditions) — identifies Wishbanc Technologies Private Limited as the service provider, describes Applicants / Teenlancers, says a job is not guaranteed to a student, and sets out rules for job offers and applicant safety.
- [Privacy Policy](https://www.funngro.com/privacy-policy) — discusses data collected from users and parent supervision / approvals for minors.

### Accuracy choices

The live public pages include specific claims about earnings, payout speed, project volume and user counts. Those figures can change and were not repeated in this redesign. The Teen page therefore avoids monthly earning estimates, payout-time promises and guarantees of project availability. It tells visitors to check the remuneration and payment mechanism in the individual job details or offer before accepting.

The Company page's mission and vision cards are explicitly labelled as a plain-language interpretation of Funngro's published purpose, not verbatim official mission / vision statements. The founding year, Shark Tank season and legal entity are attributed to Funngro's public pages. No testimonial, award, staff count or unverified partnership is invented.

### Research limitation

The public page copy and official routes were inspected through indexed and accessible web results. The site's current pages did not expose a readable visual DOM through the available page reader, so this project does not claim a pixel-level audit of the live site's exact typography, mobile breakpoints or brand tokens. The design is an original interpretation, not a reproduction of an audited style guide.

## 2. Design concept

**Company:** a restrained editorial layout, forest-green surfaces, warm off-white backgrounds, lime accents, compact labels, large display typography, and a project-flow diagram. The page emphasizes the business model, company context and trust rather than promotional performance claims.

**Teen:** a lighter, more energetic variation of the same visual system. It uses modular project-category panels, a four-step journey, practical skill framing and concise FAQs. It is designed to be energetic without becoming childish.

Both pages share a sticky header, accessible mobile navigation, consistent footer, visible focus states, responsive layouts and reduced-motion support. Illustrations are locally hosted SVG files; no stock-image service or JavaScript framework is required.

## 3. Project structure

```text
funngro-redesign/
├── index.html
├── teen.html
├── css/
│   ├── style.css
│   └── responsive.css
├── js/
│   └── main.js
├── assets/
│   ├── company-visual.svg
│   ├── teen-visual.svg
│   ├── skills-visual.svg
│   ├── funngro-company.svg
│   ├── funngro-teen.svg
│   └── favicon.svg
└── README.md
```

## 4. Run locally

No installation or build process is needed. Open `index.html` directly in a browser, or start a small local server from this folder:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## 5. Publish with GitHub Pages

1. Create a public GitHub repository named `funngro-redesign`.
2. Upload the contents of this folder to the repository root. Keep `index.html` at the root.
3. Open **Settings → Pages** in the repository.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Choose the `main` branch and `/ (root)` folder, then save.
6. Wait for GitHub Pages to publish the site. The URL will use the repository owner's GitHub username and the repository name.
7. Open both the Company page and `/teen.html` using the published URL and test them again.

### SEO URLs after deployment

The canonical links in the HTML are relative (`./` and `./teen.html`). They resolve against the live deployment path, including the GitHub Pages repository path. For stronger social sharing support, replace the relative `og:url` and `og:image` values in both HTML files with the full HTTPS URLs for the deployed pages and their corresponding SVG preview assets. Do this only after the final repository URL is known; do not leave a guessed username or domain in metadata.

For a custom domain, update both canonical links, both `og:url` values, and both `og:image` URLs to the final canonical domain before enabling it.

## 6. SEO implementation

Each page has its own title and meta description, one primary H1, ordered section headings, canonical link, Open Graph title / description / URL / image, Twitter card metadata, semantic landmarks, descriptive local image alt text and internal links to the other page. External official Funngro references open in a new tab with `rel="noopener noreferrer"`.

No organization schema, aggregate rating, review schema or earnings claims are included. The project is a redesign concept, not the official company property, so structured data identifying this repository as the Funngro business would be misleading.

## 7. Accessibility and interaction

- Skip-to-content link.
- Semantic `header`, `nav`, `main`, `section` and `footer` landmarks.
- Explicit navigation labels and current-page indicators.
- Mobile menu uses a real button with `aria-expanded` and `aria-controls`.
- Escape closes the mobile menu; navigation links close it after activation.
- Visible keyboard focus styles.
- Descriptive alternative text for non-decorative illustrations.
- Decorative icons are hidden from assistive technology.
- Native `<details>` / `<summary>` elements power the FAQ without custom scripting.
- `prefers-reduced-motion` is respected.

## 8. QA checklist

Before submission / deployment:

- [ ] Open `index.html` and `teen.html` independently.
- [ ] Test Company ↔ For teens navigation on desktop and mobile widths.
- [ ] Open the mobile menu, activate a link, click outside it and test Escape.
- [ ] Verify all local SVGs load and the `alt` text is meaningful.
- [ ] Confirm the pages do not introduce horizontal overflow at 360px, 390px, 768px, 1024px and desktop widths.
- [ ] Check one H1 per page and logical H2 / H3 order.
- [ ] Check focus visibility and reduced-motion behavior.
- [ ] Check all official external links, especially FAQ, Terms and Privacy Policy.
- [ ] Verify metadata and canonical URLs against the actual deployed address.
- [ ] Check browser console and network panel after deployment.
- [ ] Confirm the site still clearly identifies itself as an independent redesign concept.

## 9. Files to submit

Submit the whole `funngro-redesign` directory or a ZIP of this directory. The project has no external runtime dependencies and does not need a package manager.
