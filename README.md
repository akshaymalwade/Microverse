# Project Microverse — course site

A small static site for the four-week microbiology lab module at IISER Pune,
18 May – 12 June 2026. Three pages, one stylesheet, no build step.

## What's here

```
microverse-site/
├── index.html        ← public student page (schedule + announcements)
├── materials.html    ← downloads (PDFs of schedule, test, reading, primer, reference)
├── staff.html        ← TA + co-instructor page, unlinked from index
├── style.css         ← shared styling (Direction C: paper #F8F5ED, Lora + Poppins, hairlines)
├── files/            ← put PDFs here
│   ├── lab_schedule_18may_12jun.pdf
│   ├── baseline_test.pdf
│   ├── microverse_daily_reading.pdf
│   ├── Microverse_Techniques_Primer.pdf
│   └── Microverse_Deep_Reference.pdf
└── README.md         ← this file
```

## Deploying to GitHub Pages

1. Create a new repo on GitHub (any name; the URL will be `<username>.github.io/<reponame>`).
2. Push these files to the repo's `main` branch.
3. In the repo on GitHub: **Settings → Pages → Source → Deploy from a branch → main → /(root)**.
4. Wait 1–2 minutes. Your site goes live at the URL shown on the Pages settings page.

After the first deploy, every push to `main` rebuilds the site within a minute.

## Updating content

### Adding an announcement to the homepage

Edit `index.html`. Find the section marked `<!-- ============ ANNOUNCEMENTS ============ -->`.
Add a new `.announcement` block at the top of that section (newest first). Remove old ones
once they've expired.

```html
<div class="announcement">
  <div class="announcement-label">Latest update</div>
  <p>Your message here.</p>
  <div class="announcement-date">Date</div>
</div>
```

### Editing the schedule

Schedule blocks live in `index.html`, organised by week. Each day looks like this:

```html
<div class="schedule-day">
  <div class="day-date">Mon 18 May</div>
  <div class="day-content">
    <div class="day-topic">Topic for this day</div>
    <div class="day-reading">Reading: <a href="...">Title</a></div>
  </div>
</div>
```

### Marking today

To highlight the current day on the schedule, add the class `today` to the day's div:

```html
<div class="schedule-day today">
```

Remove it when the day is over. You can update this manually each morning, or write a
small script.

### Replacing a PDF

Drop the new file into `files/` with the same name as the old one. No HTML changes needed.
If you change the filename, update the link in `materials.html`.

### Updating staff details

Edit `staff.html`. The TA names, emails, and any teaching notes live there. Same workflow
as the homepage.

## Important caveat about the staff page

GitHub Pages is fully public. The `staff.html` page is **unlinked** from the homepage, so
casual visitors won't find it — but anyone with the URL can read it. Treat it as a quiet
back-channel, not a locked door.

**Do not put on the staff page:** student grades, individual student records, unreleased
exam questions, anything you would be uncomfortable having a student stumble onto.

If you need genuinely access-controlled content, host that elsewhere (a shared drive, a
university LMS, an email thread). This site is for content where public visibility is fine
or even desirable.

## About the AI-drafted documents

The daily reading, primer, and deep reference were drafted by an AI system on the basis
of a teaching brief and then reviewed. Specific factual claims (dates, citations, numerical
estimates, primer sequences) should be verified against primary sources before being
cited in any written work or graded student output.

The baseline test, schedule, and site copy are instructor-authored.

## Styling

All styling lives in `style.css`. The palette and typography follow the same Direction C
grammar as the printed PDFs (paper #F8F5ED, body #1A1815, subdued #857C6E, hairline
#B8AC97, Lora for prose, Poppins for metadata). If you want to change the look, edit the
CSS variables at the top of the file.

## Last updated

17 May 2026
