# O. Abayomi & Associates — website

Single-page site for the chambers, plus a privacy notice and a 404 page.
Static files; no build step.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The page: hero, firm, practice, process, dispute, people, FAQ, location, contact |
| `privacy.html` | Privacy notice |
| `404.html` | Not-found page (GitHub Pages serves this automatically) |
| `style.css` | All styles, including the light/dark tokens |
| `fa.css`, `fonts/`, `webfonts/` | Font Awesome and the bundled Playfair / Inter fonts |
| `img/` | Photography (`hero-900.jpg` and `office-900.jpg` are the mobile variants) |
| `sitemap.xml`, `robots.txt` | Search-engine basics |

## The enquiry form

The form has **no backend**. On submit it validates, then prepares a WhatsApp
message in the browser and shows a panel that says plainly that nothing has been
sent. The visitor completes the send inside WhatsApp.

To deliver enquiries directly instead, set the `data-endpoint` attribute on
`<form id="contactForm">` in `index.html` to a form service that accepts JSON
(Formspree, Basin, your own handler). The script then POSTs
`{ name, phone, email, service, enquiry }` and only shows a success message when
the service returns a 2xx. On failure it offers WhatsApp and telephone instead.

Either way: send a test enquiry and confirm receipt before launch.

## Things that need the firm's approval

The site deliberately avoids unverifiable claims. Check and approve:

- Practice descriptions and the "typical matters" lines.
- The process steps (enquiry → discussion → engagement).
- FAQ answers, especially fees and confidentiality.
- Team details. Only the Managing Counsel is named; chambers functions are
  described without inventing staff.
- Office hours, address, phone/WhatsApp number and the map link.
- Photography: both images are illustrative and are labelled as such. Replace
  with licensed photographs of the actual chambers when available.

## Launch notes

- Canonical URLs, Open Graph tags, the sitemap and the structured data all point
  at `https://john00-hub.github.io/abayomi-preview/`. Change them when the real
  domain is connected.
- Pages publishes from `main`.
- The theme preference is stored in `localStorage` under `oa5`; no analytics or
  cookies are used.
