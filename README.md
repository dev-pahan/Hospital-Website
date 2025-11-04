# Lanka Care - Hospital Website (HTML, CSS, JavaScript)

A responsive, static hospital/clinic website built with HTML, CSS and vanilla JavaScript. This repository contains the front-end for a demo hospital called "Lanka Care" - pages for Home, About, Services, Doctors, Contact, Medicines (shop/cart), and Checkout. It demonstrates client-side interactivity (cart, favourites, dynamic medicines listing), responsive styling, and simple form handling.

## Features
- Multi-page static site (index, about, services, doctors, contact, medicines, checkout)
- Responsive layout (mobile-first breakpoints)
- Dynamic medicines listing loaded from data/medicines.json
- Cart stored in localStorage (add, update, reset)
- Save / apply favourites (saved cart)
- Checkout form with client-side validation and card/cash selection
- Clean CSS split per page (css/*.css) and global variables (css/global.css)
- Accessible semantic HTML structure (header, nav, main, footer)

## Repository structure
- index.html - Home page
- about.html - About / branches / summary table
- services.html - Services & registration link
- doctors.html - Doctors listing
- contact.html - Contact form (posts to submit_form.php by default)
- medicines.html - Medicines catalogue and cart (scripts/order.js)
- checkout.html - Checkout form and cart summary (scripts/checkout.js)
- css/
  - global.css
  - index.css, about.css, services.css, doctors.css, contact.css, medicines.css, appointment.css, checkout.css
- scripts/
  - order.js - medicines listing, cart operations, favourites
  - checkout.js - checkout form handling
- data/
  - medicines.json - medicines catalogue used by medicines.html
- images/ - project images (logos, hero images, doctors, medicines, branches)

## How the cart & medicines work
- medicines.html fetches data/medicines.json and renders categories + items.
- Users set quantities and click Add — order.js updates the cart (keeps item, quantity, and price).
- Cart state is saved in localStorage under "cart". Use "Save to Favourites" to store under "favourites".
- Checkout reads cart from localStorage and proceeds with simple client-side confirmation (no payment gateway).

## Important notes & recommended fixes
- Card fields in checkout use plain inputs; do NOT collect real payment data in a static/demo site.
- Consider validating form inputs more strictly (email format, date constraints).
- For production: move sensitive handling (payments, storing personal data) to a secure backend and use HTTPS.

## Accessibility & performance tips
- Add meaningful alt text to all images (most are present; review).
- Compress/resize images in images/ for faster load (webp is already used, good).
- Add ARIA attributes where needed (e.g., the hamburger menu) and ensure keyboard navigation works.

## Testing & development
- Edit CSS in css/ and JS in scripts/. Open the browser devtools console to see fetch or JS errors.
- To reset stored state during development run in the browser console:
  localStorage.removeItem('cart'); localStorage.removeItem('favourites');
