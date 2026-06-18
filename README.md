---

## CSS Overview (`style.css`)

All pages share one stylesheet using CSS custom properties defined in `:root`:

- **CSS Variables** — colours (`--bg`, `--surface`, `--text`, `--text-muted`, `--error`, `--success`), fonts (`--font`, `--font-brand`), and transition speed in one place
- **Reset & Base** — removes default browser margins/padding; sets `box-sizing: border-box`
- **Header & Nav** — sticky dark header with Bebas Neue brand wordmark and Inter nav links
- **Buttons** — four variants: `.btn-primary`, `.btn-ghost`, `.btn-outline`, `.btn-ghost-dark`
- **Hero** — full-width centred banner with large Bebas Neue heading and eyebrow label
- **Perks Strip** — four-column info strip below the hero (free delivery, returns, etc.)
- **Featured Section** — max-width product grid with section header and CTA
- **Cards** — dark surface cards with hover lift, `object-fit: cover` images, name and price
- **Statement Section** — centred brand quote / mission block
- **Page Hero** — shared top banner used on About, Contact and Enquiry pages
- **Stats Strip** — four-column stat row used on the About page
- **About Content** — single-column prose layout with `.about-block` and `.value-item` panels
- **Contact Layout** — two-column CSS Grid (form left, info right); collapses to one column on tablet
- **Forms** — shared input, textarea and select styling used on Contact and Enquiry pages
- **Validation** — `.error-msg` (red) and `.success-msg` (green) inline feedback
- **Enquiry** — `.enquiry-wrapper`, `.price-display`, `.enquiry-summary`, `.summary-note`
- **Products Page** — `.products-page`, `.filter-bar`, `.filter-btn` with active state, `.category-heading`, `.no-results`
- **Lightbox** — fixed full-screen modal with image, name, description, price and enquire link
- **Footer** — three-column CSS Grid (brand 2fr, navigate 1fr, connect 1fr) with bottom bar
- **Responsive** — breakpoints at 960px, 768px, 600px

---

## JavaScript Features

### Details.html
- **Real-time search** — search input filters product cards by name as the user types; cards that do not match are hidden instantly
- **Category filter buttons** — six buttons (All / Hoodies / T-Shirts / Bottoms / Footwear / Accessories); clicking a button hides all cards outside that category and auto-hides the corresponding section heading
- **Lightbox gallery** — clicking any product card opens a modal overlay showing the product name, description, price and an "Enquire About This Item" link; the modal closes on background click, the × button, or the Escape key

### enquiry.html
- **Dynamic dropdowns** — selecting a product category automatically populates the item dropdown with the correct products and prices
- **Live price display** — a highlighted price box appears as soon as a specific item is chosen
- **JavaScript validation** — checks that all required fields are filled and correctly formatted before submission (name length, email regex, phone number format)
- **Enquiry summary** — on valid submission the form is replaced by a formatted summary of the enquiry; a "Submit Another Enquiry" button resets and restores the form

### contact.html
- **JavaScript validation** — checks name length, email format, message type selection and message length before allowing submission
- **mailto construction** — on valid submission a `mailto:` link is built with the subject and body pre-filled from the form, and the user's email client is opened automatically

---

## SEO

Each page includes:
- Unique `<title>` tags with the brand name
- `<meta name="description">` with page-specific descriptive content
- `<meta name="keywords">` with relevant terms
- `<meta name="author">` attribution
- `alt` attributes on all product images
- Logical heading hierarchy (H1 brand → H2 section → H3 sub-section)
- Mobile-friendly `<meta name="viewport">` tag on every page

A `robots.txt` file instructs search engine crawlers to allow all pages.

---

## Responsive Breakpoints

| Breakpoint | Applies to |
|------------|------------|
| `max-width: 960px` | Tablet — contact layout collapses to one column; footer switches to two-column grid; stats and perks strips wrap |
| `max-width: 768px` | Narrow tablet — header stacks vertically; section padding reduced; footer collapses to one column |
| `max-width: 600px` | Mobile — single-column product grid; hero actions stack; perks strip hidden; filter buttons centred |

---

## Fonts Used

- **Bebas Neue** — headings and brand name (loaded from Google Fonts)
- **Inter** — body text, labels and buttons (loaded from Google Fonts)

The font stack also includes `-apple-system` and `BlinkMacSystemFont` so the site uses the native system font (SF Pro) on Apple devices automatically. Both fonts load via `<link>` in the `<head>` of each page and fall back to Segoe UI / Roboto / sans-serif if Google Fonts is unavailable.

---

## Images

Product images are stored one folder up (`../`) from the HTML files.
Example: `<img src="../black hoodie.jpg" alt="Black Hoodie - UrbanDrip Clothing">`

All images include descriptive `alt` attributes for accessibility and SEO.
Images use `object-fit: cover` so they display consistently regardless of original size.

---

## How to Run

Open `index.html` in any browser. No server or installation needed.

---

## Built With

- HTML5
- CSS3 (Flexbox + CSS Grid + Custom Properties)
- JavaScript (ES5/ES6, no libraries)
- Google Fonts (Bebas Neue + Inter)

---

## Changelog

### Part 3 — 2026-06-18

#### New Files
- **`enquiry.html`** — New product enquiry page with:
  - Category dropdown that dynamically populates an item dropdown (JS)
  - Live price display when a specific product is selected (JS)
  - Full JavaScript validation: name (min 2 chars), email (regex), phone (7–15 digit regex), all dropdowns required
  - On valid submission: form hidden, formatted enquiry summary displayed with all captured details and a confirmation message
  - "Submit Another Enquiry" button resets and restores the form
- **`robots.txt`** — Added crawler instructions file to allow all pages

#### New Features
- **Lightbox gallery** (`Details.html`) — Clicking any product card opens a full-screen modal overlay showing the product name, a descriptive blurb, price and an "Enquire About This Item" link; closes on background click, × button or Escape key press
- **Real-time product search** (`Details.html`) — Text input filters visible product cards by name as the user types; category section headings auto-hide when no products in that category are visible
- **Category filter buttons** (`Details.html`) — Six filter buttons (All / Hoodies / T-Shirts / Bottoms / Footwear / Accessories) with active state styling; combine with search for precise filtering
- **Contact form JS validation** (`contact.html`) — Validates name length (≥ 2 chars), email format (regex), message type selection (required), message length (≥ 10 chars); shows inline error messages below each field; on success builds and opens a `mailto:` link with all data pre-filled
- **Message type dropdown** (`contact.html`) — Added `<select>` for enquiry type: General Enquiry, Order Issue, Returns & Refunds, Product Question, Complaint, Compliment
- **Enquire nav link** — Added link to `enquiry.html` in the navigation bar on all pages

#### SEO Improvements (all pages)
- Added `<meta name="description">` with unique, page-specific content to every page
- Added `<meta name="keywords">` with relevant streetwear and South Africa search terms
- Added `<meta name="author">` tag to every page
- Updated `<title>` tags to be descriptive and consistently include the brand name
- Added `alt` attributes to all product images on `index.html`
- Ensured logical heading hierarchy (H1 brand name → H2 section titles) across all pages

#### Styling Updates (`style.css`)
- Full visual redesign: deep black/dark theme (`--bg: #0a0a0a`, `--surface: #141414`) replacing the original lighter palette
- Swapped body font from DM Sans to **Inter** with an `-apple-system` / `BlinkMacSystemFont` system font stack for native SF Pro on Apple devices
- Rewrote all CSS variables: `--bg`, `--surface`, `--surface-2`, `--border`, `--border-hover`, `--text`, `--text-muted`, `--text-dim`, `--success` (#34c759), `--error` (#ff3b30), `--font`, `--font-brand`, `--transition`, `--max-w`
- Added four button variants: `.btn-primary`, `.btn-ghost`, `.btn-outline`, `.btn-ghost-dark`
- Added hero components: `.hero`, `.hero-inner`, `.hero-eyebrow`, `.hero-sub`, `.hero-actions`
- Added `.perks-strip` and `.perk` for the four-item strip below the home hero
- Added `.section-header`, `.section-label`, `.section-cta` for featured section
- Redesigned `.card` with border, hover lift (`translateY(-5px)`) and `box-shadow`
- Added `.statement-section` and `.statement-inner` for the brand quote block
- Added `.page-hero` and `.page-hero-eyebrow` shared across About, Contact and Enquiry
- Added `.stats-strip` and `.stat-item` for the About page stats row
- Added `.about-block`, `.value-item` for About page content
- Added `.contact-layout` (CSS Grid 2-column), `.contact-form-col`, `.contact-info-col`, `.col-heading`, `.col-sub`, `.info-block`, `.info-divider`
- Added `.enquiry-wrapper`, `.price-display`, `.enquiry-summary`, `.summary-note`
- Added `.products-page`, `.products-page-header`, `.filter-bar`, `.filter-buttons`, `.filter-btn`, `.category-heading`, `.no-results`
- Added `.lightbox`, `.lightbox-content`, `.lightbox-close`, `.lightbox-img`, `.lightbox-body`, `.lightbox-price`, `.lightbox-enquire`
- Redesigned `footer` with CSS Grid three-column layout: `.footer-inner`, `.footer-brand`, `.footer-col`, `.footer-bottom`
- Added three responsive breakpoints: 960px, 768px, 600px
- Added visibility fix overrides for brighter `--text-muted`, `--text-dim` and form input border colours

#### Bug Fixes / Improvements (from Part 2 feedback)
- Fixed duplicate `<!DOCTYPE html>` declaration that appeared in the original `contact.html` file
- Corrected featured product prices on `index.html` to use Rand (R) values consistent with `Details.html`
- Standardised nav structure across all pages (same links, same order)
- Removed stray duplicate `<footer>` tags that appeared in the combined file
