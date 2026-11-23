# TalentBridge — Week 1

## Integrated capstone

This task is part of the broader [TalentBridge internship and placement platform](https://github.com/syedghulamahmed/Capstone), which consolidates the platform architecture and end-to-end workflow.


Responsive marketing landing page and internal dashboard shell for the NeuroFive Solutions Full Stack Web Development internship task.

## Files

- `landing.html` — public marketing page.
- `dashboard.html` — responsive logged-in dashboard shell.
- `styles.css` — shared mobile-first design system and component styles.
- `README.md` — project documentation and testing notes.

## Run locally

No build step or dependencies are required.

1. Download/clone the repository.
2. Open `landing.html` directly in Chrome/Firefox, or use VS Code Live Server.
3. Open `dashboard.html` to inspect the dashboard.
4. Use DevTools responsive mode to test the breakpoints.

## CSS architecture

1. CSS custom properties in `:root` provide the shared color, spacing, radius, shadow, typography, and layout tokens.
2. A small reset and shared primitives establish predictable box sizing, focus states, containers, buttons, and accessibility utilities.
3. Components use lightweight BEM-style names such as `.feature-card__icon` and `.stat-card--modifier`.
4. The stylesheet is organized by tokens, shared primitives, landing components, dashboard components, and responsive breakpoints.
5. Mobile styles are the default; tablet and desktop rules progressively enhance the layout.
6. Flexbox handles one-dimensional navigation/toolbars, while CSS Grid handles feature, statistics, dashboard, and form layouts.
7. The dashboard table is contained in `.table-wrapper`, allowing horizontal scrolling without creating page-level overflow.

## Responsive strategy

- **Mobile:** single-column content, hamburger dashboard navigation, bottom dashboard navigation, horizontally scrollable table.
- **Tablet (640px+):** two-column cards/forms and improved content spacing.
- **Desktop (900px+):** full navigation, persistent sidebar, four stat columns, two-column dashboard panels.
- **Wide desktop (1200px+):** additional dashboard spacing and panel padding.

## Accessibility

- Semantic landmarks: `header`, `nav`, `main`, `section`, `article`, `footer`, `aside`.
- Skip links are provided on both pages.
- Form inputs have explicit labels and required-field indicators.
- Interactive elements receive visible `:focus-visible` outlines.
- Table headings use `scope="col"`.
- The testimonial section includes a responsive `<picture>`/`srcset` image with descriptive `alt` text, demonstrating responsive image handling.
- `prefers-reduced-motion` is respected.
- The page avoids body-level horizontal overflow; the dashboard table scrolls only inside its wrapper.

## SaaS dashboard research notes

For the visual direction, the dashboard borrows three common SaaS layout patterns seen across products such as Linear, Notion, and Vercel:

1. **Persistent left navigation on desktop:** keeps primary workspace navigation visible while content changes.
2. **Compact top utility bar:** separates search, notifications, and account controls from the main workspace.
3. **Information-dense cards and tables:** surfaces important metrics first, then gives users a scannable operational list.

These patterns were selected because they reduce navigation friction and create a predictable workspace hierarchy without depending on a JavaScript framework.

## Accessibility / Lighthouse checklist

Before submitting:

- Run Lighthouse Accessibility on `landing.html`.
- Run Lighthouse Accessibility on `dashboard.html`.
- Target **90+ accessibility** on both pages.
- Test keyboard-only navigation with `Tab`, `Shift+Tab`, `Enter`, and `Space`.
- Test at approximately **375px**, **768px**, and **1440px** viewport widths.
- Confirm there is no horizontal page scroll at each breakpoint.
- Check color contrast in DevTools.
- Test form focus and invalid states.

## Screenshot checklist

The repository now includes six breakpoint previews in `screenshots/` for the required mobile, tablet, and desktop documentation. For an official submission, you should replace these previews with browser/DevTools captures if your reviewer specifically requires Chromium screenshots.

The repository includes:

```text
screenshots/
├── landing-mobile.png
├── landing-tablet.png
├── landing-desktop.png
├── dashboard-mobile.png
├── dashboard-tablet.png
└── dashboard-desktop.png
```

Then optionally embed them here:

```md
## Screenshots

### Landing — mobile
![Landing mobile](screenshots/landing-mobile.png)

### Landing — tablet
![Landing tablet](screenshots/landing-tablet.png)

### Landing — desktop
![Landing desktop](screenshots/landing-desktop.png)

### Dashboard — mobile
![Dashboard mobile](screenshots/dashboard-mobile.png)

### Dashboard — tablet
![Dashboard tablet](screenshots/dashboard-tablet.png)

### Dashboard — desktop
![Dashboard desktop](screenshots/dashboard-desktop.png)
```

## Included breakpoint previews

### Landing — mobile
![Landing mobile](screenshots/landing-mobile.png)

### Landing — tablet
![Landing tablet](screenshots/landing-tablet.png)

### Landing — desktop
![Landing desktop](screenshots/landing-desktop.png)

### Dashboard — mobile
![Dashboard mobile](screenshots/dashboard-mobile.png)

### Dashboard — tablet
![Dashboard tablet](screenshots/dashboard-tablet.png)

### Dashboard — desktop
![Dashboard desktop](screenshots/dashboard-desktop.png)

See `TEST_REPORT.md` for the verification summary.

## Git workflow

Use meaningful incremental commits, for example:

```bash
git init
git add landing.html styles.css
git commit -m "feat: build responsive TalentBridge landing page"

git add dashboard.html
git commit -m "feat: add responsive dashboard shell"

git add README.md
git commit -m "docs: add project architecture and testing notes"

git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/talentbridge-week1.git
git push -u origin main
```

## Submission

Submit the public GitHub Pages URL or another public deployment URL in the NeuroFive portal.

Example GitHub Pages URL:

`https://YOUR_USERNAME.github.io/talentbridge-week1/`

> TalentBridge is a fictional product created for this internship exercise.
