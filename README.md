# Project Microverse — course site

A small static site for the four-week microbiology lab module, 18 May – 12 June 2026.
Two pages, one stylesheet, no build step.

## What's here

```
microverse-site/
├── index.html        ← public schedule page
├── team.html         ← TA + co-instructor page, unlinked from index
├── style.css         ← shared styling (Direction C: paper #F8F5ED, Lora + Poppins, hairlines)
└── README.md         ← this file
```

## Deploying to GitHub Pages

Push files to `main`. In the repo: **Settings → Pages → Source → Deploy from a branch
→ main → /(root)**. Site goes live at `<username>.github.io/<reponame>` within a minute or two.

Every subsequent push to `main` rebuilds the site.

## Updating content

### Announcements

Edit `index.html`. The announcement block lives near the top:

```html
<div class="announcement">
  <div class="announcement-label">Latest update</div>
  <p>Your message here.</p>
  <div class="announcement-date">Date</div>
</div>
```

Add new announcements at the top, remove old ones once they've expired.

### Schedule

Schedule blocks live in `index.html`, organised by week. Each day looks like this:

```html
<div class="schedule-day">
  <div class="day-date">Mon 18 May</div>
  <div class="day-content">
    <div class="day-topic">Topic for this day</div>
    <div class="day-reading">Reading: <em>Title</em></div>
  </div>
</div>
```

### Marking today

To highlight the current day, add the class `today` to the day's div:

```html
<div class="schedule-day today">
```

Remove it when the day is over.

### Team page

Edit `team.html`. Names, emails, and notes live there.

## Important caveat about the team page

GitHub Pages is fully public. The `team.html` page is **unlinked** from the homepage, so
casual visitors won't find it — but anyone with the URL can read it. Treat it as a quiet
back-channel, not a locked door.

**Do not put on the team page:** student grades, individual student records, unreleased
exam questions, anything you would be uncomfortable having a student stumble onto.

## Styling

All styling in `style.css`. Palette and typography follow Direction C (paper #F8F5ED,
body #1A1815, subdued #857C6E, hairline #B8AC97, Lora for prose, Poppins for metadata).
CSS variables at the top of the file if you want to tweak.

## Last updated

18 May 2026
