# SAME@SDSU Website
The official website for the Society of American Military Engineers (SAME) student chapter at San Diego State University (SDSU) is live at https://same-sdsu.github.io/.

### Overview & Features
This is a static HTML-based website. Features include:
- Information & social media links.
- Google Calendar integration.
- Events showcase and photo slideshow.
- Light/dark mode toggle with system preference detection.
- Officer profiles and a collapsible archive of past officers.

To view locally, clone this repository and double-click `index.html`.

### Deploying Changes
This site is designed to be pushed to GitHub and hosted by GitHub Pages.

Push changes to the [main branch](https://github.com/SAME-SDSU/same-sdsu.github.io) and they will reflect automatically within 1-2 minutes.

### Updating the Site

<details> 
<summary>Updating Next Event</summary>

All event content is located in `index.html`. Search for `<h3>Next Event</h3>` to jump to the correct section.

1. Update the title, date, and description:
```html
<div class="event-title">Event Name</div>
<div class="event-meta">Date: M/DD • Time: H:MMpm • Location: Venue</div>
<p>Brief description of the event.</p>
```

2. Toggle the registration button:

```html
<!-- No registration -->
<span class="btn" style="pointer-events: none; opacity: 0.6;">No Registration Needed</span>

<!-- Registration open -->
<a class="btn" href="https://your-link-here" target="_blank" rel="noopener">Register Here!</a>
```

</details>

<details> 
<summary>Updating Photo Slideshow</summary>

Slideshow images are stored in `images/slideshow/` and follow sequential numbering (e.g., `1.jpeg`, `2.png`, `3.jpg`).

1. Add the image file to `images/slideshow`

2. Search for `class="slideshow"` in `index.html` and insert a new slide block immediately before `<div class="slide-controls">`:
```html
<div class="slide">
  <img src="images/slideshow/4.jpg" alt="Short description of photo">
</div>
```

Navigation and dot indicators update automatically.

To remove a slide, delete its `<div class="slide">` block and remove the corresponding image file.

</details>

<details> 
<summary>Updating Socials & Contact Information</summary>

Links appear in two locations: `Get Involved` and `Contact`. Find and update as needed.

</details>

<details> 
<summary>Updating Officers, Officer Photos, and Past Officer Archive</summary>

There are two officer sections in `index.html`:
- The Current team inside `<p class="section-sub">20XX – 20XX Team</p>`.
- The Past team archive inside `<div id="archivePanel">`, which expands when "Show Past Officers" is clicked.

At the start of each new term:
1. Copy the entire current officers grid.
2. Paste it at the top of `archivePanel`, above the existing archive content such that previous officers are not overridden.
3. Add a `<p class="archive-meta">20XX – 20XX Team</p>` label directly above the grid you just pasted.
4. Populate the current grid with the new team's information and update the `section-sub` year label.

This preserves a full history of all past officer teams.

Officer card template:
```html
<div class="card person">
  <div class="avatar">
    <img src="images/officers/filename.png" alt="First Last">
  </div>
  <div>
    <div class="role">Role Title</div>
    <div class="name">First Last</div>
    <div class="event-meta">Major</div>
  </div>
</div>
```

Adding an officer photo:
1. Crop as needed.
2. Save as `.png` or `.jpg` in `images/officers/`.
3. Reference the filename in the card's `src` attribute.

If a position is vacant, either omit the card or leave `src` pointing to a placeholder image.

</details>

<br>

Built & maintained by Tanish Gheewala. For questions, contact tanishgheewala@gmail.com.