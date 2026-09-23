# Deploying RoboSimunomy to GitHub Pages

1. Create a repo named exactly: robosimunomy.github.io (must match your GitHub username exactly)
2. Upload every file in this folder to the root of that repo (index.html, about.html, assets/, etc.)
3. In the repo: Settings -> Pages -> Source: "Deploy from a branch" -> Branch: main / (root) -> Save
4. Wait 1-2 minutes, then visit https://robosimunomy.github.io

## Contact form
The contact form uses FormSubmit (https://formsubmit.co) — a free service, no signup needed.
The FIRST time someone submits the form, FormSubmit will send a confirmation email to
robosimunomy@gmail.com asking you to activate that endpoint. Click the link in that email once,
and every submission after that will land directly in your inbox.

## Sign In / Sign Up pages
These are DEMO ONLY. This is a static site (GitHub Pages) with no backend or database, so there is
no way to have a real, secure login system here. The demo login (username: emon, password: emon)
is just client-side JavaScript for show — anyone can view the password in the page source. Do not
use this for anything that needs real security. If you want real user accounts later, you'd need a
backend service (e.g. Firebase Authentication, which has a free tier and works fine with GitHub Pages).

## What still needs your attention
- Replace placeholder images (logo, team photos, hero image) with your own — you mentioned you'll
  do this yourself.
- The two blog pages (blog-grids.html, blog-details.html) still have generic placeholder article
  text (not rebranded content) — only the navigation, footer, and title were updated on those.
- Footer legal links (Privacy Policy, Terms of Service) are placeholders that don't go anywhere yet.

## Update (nav fix + Founder page)
- Fixed a bug where clicking Home / About / Pricing / Team in the top nav did nothing outside the
  Pages dropdown. Root cause: those links used same-page anchor hrefs (#home, #about, etc.) meant
  for a single scrolling page, but a script hijacked every click with e.preventDefault() before
  trying to scroll to that anchor — which doesn't exist on most pages, so nothing happened. Fixed
  by pointing Home/About/Pricing/Team/Contact at real pages (index.html, about.html, pricing.html,
  about.html#team, contact.html) and only letting the smooth-scroll script handle genuine "#"
  anchors. The logo already linked to index.html everywhere, so it's your universal Home button.
- Added a new Founder page (founder.html) built from your abs-emon portfolio — bio, education,
  experience, skills, projects (with images), publications, and a CV download. Linked from:
  the "Meet the Founder" button and "Emon" name on the About/Home team card, and a new "Founder"
  item in the Pages dropdown on every page.
