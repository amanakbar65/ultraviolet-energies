# Ultra Violet Energies: website

A single-page, fully self-contained marketing website for **Ultra Violet Energies Pvt. Ltd.**, built from the company brochure, the 10 MW Detailed Project Report and the 4 MW Solar-as-a-Service implementation agreement.

Everything lives in `index.html` (HTML, CSS and JavaScript). There is no build step and the only external request is the Jost font from Google Fonts.

## Preview

Open `index.html` in a browser, or serve the folder:

```bash
npx serve .
```

## Deploy

Upload `index.html` to any static host: GitHub Pages, Netlify, Vercel, Cloudflare Pages, S3, or the web server behind `www.ultravioletenergies.com`.

## Sections

| Section | Interactive element |
|---|---|
| Hero | Brand orb recreated from the brochure cover, with the official logo lockup |
| About | Draggable 3D network globe, client segments, 5 guiding principles |
| The model | Responsibility split, capacity-fee equation, 25-year journey slider |
| Why subscribe | 6 brochure benefits, comparison with buying a plant or staying on grid |
| Technology | Clickable power-flow explorer (sun to facility, plus SCADA, cleaning, grid, DG) |
| Savings estimator | Consumption, tariff (₹6–10) and solar-coverage (30–90%) sliders; bill comparison; monthly and 25-year charts |
| Implementation | 24-week Gantt with week scrubber and auto-play; onboarding and COD checklists |
| Operations & support | O&M scope, service levels, fault-reporting process |
| Impact & ESG | Animated impact counters (per 10 MW), E/S/G tabs, SDG alignment |
| FAQ / Contact | Accordion FAQ; validated enquiry form |

## Logo

The sunburst mark is an inline SVG traced from the official logo: 36 spokes at 10° intervals, each a hairline carrying one thick band that steps outward around the circle to form the spiral. Two variants live in the SVG sprite at the top of `<body>`:

- `#sb`: exact proportions, used large in the hero lockup.
- `#sb-s`: weight-adjusted for small sizes, used in the nav, footer and favicon.

## Configuration

At the top of the `<script>` block in `index.html`:

```js
const CONFIG = {
  ratePerKwMonth: 850,   // ₹ per kW per month used by the savings estimator
  yieldPerKw: 1587,      // modelled year-1 units per kW
  contactEmail: 'ultravioletenergies@gmail.com', // enquiries open a pre-filled email to this address
  formEndpoint: ''       // optional form-service URL (Formspree, Getform, …)
};
```

Contact details (email `ultravioletenergies@gmail.com`, phone `+91 98869 00000`) appear in the contact section, the footer and the structured data in `<head>`.

The enquiry form currently opens the visitor's email app with the request pre-filled. To have enquiries delivered without relying on the visitor's email app, create a free form endpoint (for example Formspree) and paste its URL into `formEndpoint`.

The `₹850 / kW / month` rate also appears as static text in the Model section, the estimator note and the FAQ. Update those if the published rate changes.
