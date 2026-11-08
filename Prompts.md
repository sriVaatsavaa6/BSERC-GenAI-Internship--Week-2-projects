# Prompts

# PROMPT 1: AUTO RALLY (Project-8)

you are an android developer who knows kotlin, game physics and testing.

make a native android racing game called **AUTO RALLY**. the player drives a yellow and green indian auto-rickshaw around a closed track, finishes exactly 3 laps, collects coins and tries to beat the saved best time. it must be a real playable game, not a mockup or webview.

- use kotlin, jetpack compose and canvas
- realistic 3 wheel auto, raised third-person or 2.5D view with smooth camera
- driving physics with speed, braking, steering and momentum (frame-rate independent)
- touch buttons for left, right, accelerate, brake (working together), keyboard WASD/arrows, space to pause
- countdown, 3 laps with checkpoints, then results screen
- HUD with lap, time, speedometer, coins and pause/mute
- coins, obstacles (cones, barriers, oil), power-ups (speed boost, shield)
- sound effects and music with toggles
- save best time locally with a reset button
- screens: splash, menu, game, pause, results, how to play, settings
- dark charcoal with yellow and green, premium look

1. native kotlin only, no website or webview
2. lap counting can't be cheated, coins collected once per race
3. best time must stay after restart
4. works fully offline, no internet permission
5. every button must work
6. test on a real phone in airplane mode and fix crashes before giving it to me.

---

# PROMPT 2: BILL BOOK (Project-7)

you are an android developer who knows kotlin, jetpack compose, room database and UI design.

make a native android billing app for a small shop in india. the owner can add products, make invoices, generate a UPI QR for the exact amount, share invoices and see sales history. it must work offline. give it a good app name (not "Bill Book").

- use kotlin, jetpack compose, room, MVVM
- shop profile: name, logo, address, phone, GSTIN, UPI ID, invoice prefix, default GST
- products: add, edit, delete, search (sample: Rice ₹60/kg, Milk ₹30/litre)
- invoice: pick products, quantity, discount, GST, customer details, preview before saving
- UPI QR: `upi://pay?pa=UPI_ID&pn=NAME&am=AMOUNT&cu=INR&tn=INVOICE_NO`
- save invoice as PNG and PDF, share by sharesheet and whatsapp, print
- dashboard with today's sales, bill count and recent bills
- history with search and filters, plus daily/weekly/monthly reports
- sample shop "Sharma Stores" on first run with an option to delete sample data
- navy, white and grey design with a small teal accent, no emojis

1. native kotlin + compose only, no website or webview
2. no float math for money, use paise or decimal
3. QR must have the right UPI ID and exact amount
4. don't mark Paid just because QR was shown, status is set manually
5. old invoices must not change when products or settings change
6. no fake buttons or fake success messages
7. test at least 5 invoices with discount and GST, and test offline
8. give me the APK and source code

---

# PROMPT 3: YOUTUBE FOCUS BOARD (Project-9)

you are a chrome extension developer who knows manifest v3, javascript and UI design.

make a chrome extension called **YouTube Focus Board** that makes youtube better for studying. it hides distractions, asks why you are here before letting you watch, and has a study list and notes.

- files: manifest.json, content.js, content.css, popup.html, popup.js, icons (16, 32, 48, 128), README.md
- popup with 2 tabs: Distractions and Study
- hide switches for home feed, sidebar, end screen, shorts, comments, mixes, merch, video info, header, explore, subscriptions, autoplay, annotations
- search box, master Power switch, light/dark theme
- presets: Study, Lecture, Relaxed, Off (highlight the one matching current settings)
- focus gate that covers youtube, pauses video and asks **"I'm here to..."**, needs a reason, then unlocks for 60 minutes with a countdown
- study list with checkboxes (saved videos can skip the gate if the switch is on)
- timestamp notes, click to jump, export to markdown
- Focus pill on page, opens panel with Alt+N
- daily usage tracking (active time only), daily goal and warning
- home feed message: "Home feed hidden by Focus Board. Search for what you came to study."
- blue and red glassmorphism design, no emojis
- credit at bottom of popup, gate and panel: **Made with ♥ by Akshay Srivatsava. B** (red heart)

1. manifest v3, only the `storage` permission
2. plain HTML, CSS, JS only, no libraries or CDN
3. works offline, no data sent anywhere
4. save everything in chrome.storage.local
5. hiding must keep working when youtube changes pages without reload
6. run `node --check` on all JS files
7. test on real youtube, not just the popup
8. README with install steps and a "Done when" checklist

---

# PROMPT 4: FORM PHOTO FIXER (Project-2)

you are a front-end developer who knows vanilla JavaScript, the canvas API and clean UI design.

make a single HTML file called **Form Photo Fixer**. it resizes and compresses a passport photo and a signature to the exact size (cm) and file size (KB) that an online form asks for. it must work offline and nothing gets uploaded anywhere. no libraries, no CDN, no backend.

- header with small label "Image preparation workspace", title "Form Photo Fixer", and the line "Photo and signature, resized and compressed to each form's exact rules. Works offline — nothing is uploaded." plus a small online/offline status text
- "Output specifications" card with a form preset dropdown and a pixel density box (default 200 dpi, range 72 to 600)
- 3 sample presets (width × height in cm, min–max KB):
  - Exam form A (SSC-style): photo 3.5×4.5, 20–50 KB, signature 4×2, 10–20 KB
  - Entrance exam B (JEE/NEET-style): photo 3.5×4.5, 10–200 KB, signature 3.5×1.5, 4–30 KB
  - Job application C (generic): photo 3.5×4.5, 10–100 KB, signature 6×2, 5–50 KB
- collapsible "Edit rules or save a custom preset": fields for preset name, official notice link, photo width/height/min KB/max KB, signature width/height/min KB/max KB. save custom presets in localStorage, with a delete button for custom ones only
- two cards side by side, Photo and Signature. each has a drop zone (drag and drop, paste with Ctrl+V, or tap to choose; JPG, PNG, WebP) and a canvas preview you can drag to move, zoom with mouse wheel or slider (0.5 to 3), rotate 90°, reset, and brightness (60–150) and contrast (60–160) sliders
- photo only: face guide overlay (dashed oval + shoulder line) with a checkbox, a "Centre face" button that uses the browser FaceDetector only if it exists, and an optional "Name and date strip" at the bottom of the photo (name text + date)
- signature only: "Clean paper and darken ink" checkbox (grayscale levels so the background goes white)
- auto fit: convert cm to pixels using the dpi, export JPEG, binary search the quality to get under the max KB. if the file is under the min KB raise the dpi, if it can't fit lower the dpi. write the dpi into the JPEG header
- after fitting show a size meter ("x KB of y KB limit") and a checklist with ✓ ✗ !: under max, above min, exact px = cm at dpi + quality, and "re-opened and verified as a valid JPG"
- buttons: download photo, download signature, download both, and download a report (.txt) with preset, required vs actual size and KB
- note under the buttons: presets are samples, check every limit against the official notice
- footer: "Engineered by **Akshay Srivatsava. B.**"
- design: calm sage and olive green, light grey-green background, accent #8FB339, dark green #4B5842, soft tea green #C7D59F, big rounded cards, gradient header with a faint ring on the right, dashed upload boxes, Google Sans / Roboto font, no emojis

1. one HTML file, plain HTML + CSS + JS only
2. no uploads, no network calls, works in airplane mode
3. respect photo orientation (EXIF) and show a clear message for non-image files and HEIC
4. final file must be under the max KB and the real pixel size must match the cm and dpi
5. recompress only after changes (wait a short moment, ignore old runs)
6. works with mouse, touch and keyboard, and is usable on a phone
7. test with at least 3 real photos and 3 signatures on all 3 presets and check the numbers

---

# PROMPT 5: RESUME BUILDER (Project-3)

you are a front-end developer who knows vanilla JavaScript, print CSS, LaTeX and UI design.

make a single HTML file called **Folio Resume Builder & ATS Studio**. it builds A4 resumes, edits LaTeX, checks ATS score and writes cover letters, all in the browser with no server and no libraries. data never leaves the device.

- floating glass header with the Folio logo (logo only shows on the home page) and 5 tabs: Home, Builder, LaTeX Studio, ATS Scanner, Cover Letter
- header buttons: resume version dropdown + "+ Version", undo and redo (Ctrl+Z / Ctrl+Y, last 40 steps), Load Sample Data, Remove Sample / Clear, Export and Import (JSON), Export PDF, and a "Next: ..." button that goes through the steps in order
- **Home:** title "Precision Resume Engineering & ATS Diagnostics.", short paragraph, 3 buttons (Start Building Resume, Open ATS Scanner, LaTeX Studio), 4 clickable step cards (builder, LaTeX, ATS, cover letter) and 4 feature cards (5 A4 templates, deterministic ATS scoring, native LaTeX, zero cloud). no fake reviews or fake numbers
- **Builder:** sidebar + live A4 preview
  - Folio ATS score ring with label, word count, page count, tips list, "Bullet Optimizer" button
  - 6 templates: Studio Pro (split header), Cupertino, Academic (Jake's Tech), Classic (serif centred), Executive (banner header), Timeline (left dates)
  - accent colour picker, font size 9–12 pt, line spacing 1.2–1.6, page margin 8–18 mm
  - drag and drop to reorder sections
  - accordion forms: personal details (name, headline, email, phone, location, links), summary, experience, projects, education, certifications (role, company, dates, highlights one per line), skills (comma separated)
  - preview zoom bar: −, Fit, 100%, +, an "Eye Heatmap" toggle (recruiter 6-second F-pattern simulation, say it's a simulation), and Export MD
- **LaTeX Studio:** .tex generated from the builder in 4 layouts (2-column sidebar, Jake's technical, executive split-banner, academic CV). code editor with line numbers, live typeset preview, edits update the preview, "Sync from Builder", Download .tex, Copy Source, Open in Overleaf
- **ATS Scanner:** source is either the active builder resume or an uploaded PDF / DOCX / TEX / TXT / MD (read locally, PDF and DOCX using DecompressionStream) or pasted text. box for a job description + "Load Sample JD". "Run ATS Diagnostics" shows:
  - score out of 100 from rules: contact info (12), standard headings (20), word count 350–900 (10), action-verb bullets (15), numbers in bullets (15), date anchors (5), single-column parseability (8), and job keyword match (20, only if a JD is given)
  - grade: 80+ Executive Grade · ATS Ready, 60+ Competitive · Room to Optimize, below that Needs Structural Polish
  - matched keywords and missing keywords as chips, click a missing one to inject it into Skills
  - bullet by bullet audit (action verb? metric? length?) and the raw text the parser read
- **Bullet Optimizer** popup: "Accomplished [X] as measured by [Y], by doing [Z]". shows each bullet with Action Verb / Quantified badges, suggests a rewrite, and an apply button. rule based, not AI, and say so
- **Cover Letter:** company, hiring manager, role, tone (Executive & Impact-Driven, Technical & Quantitative, Collaborative & Story-Driven). "Generate" builds a letter from the resume and top skills, editable text box, live A4 preview, export PDF
- sample data: 2 fake profiles (example.com emails), clearly fake, easy to remove
- data saved in localStorage as multiple versions with a schema version and a safe migration for old data
- print CSS so Export PDF prints only the clean A4 page(s), no UI
- design: warm light off-white canvas (#f4f4f0), frosted glass panels with blur, yellow (#facc15) and black (#111) corporate palette, system font stack (SF Pro / Inter), rounded cards, small toasts for actions, light and quiet animations. no emojis
- footer: "Made with ♥ by **Akshay Srivatsava. B**" (red heart)

1. one HTML file, plain HTML + CSS + JS only, no external libraries, fonts or APIs
2. works offline and sends nothing anywhere
3. what you see in the A4 preview is what prints, and page count must be correct
4. ATS score must come from real rules and the same text gives the same score, no random numbers
5. escape all user text so nothing breaks the page
6. undo / redo, version switching, import / export must not lose data
7. every button and tab must work, no fake buttons or fake success messages
8. test with the sample data, an empty resume and a long 2 page resume, then print to PDF and check it
9. fix bugs and layout problems before giving it to me

---

# PROMPT 6: YOUR OWN SKILL (Project-16)

you are an AI developer who knows how agent skills (a folder with a SKILL.md) work and how oral exams (vivas) are taken.

this is project 16, and i'm picking the /viva option. make a skill called **/viva** that works in a brand-new session. i give it my notes (PDF or pasted text) and type /viva, and it asks me viva questions one at a time and scores me at the end.

first do the viva once in a normal chat with sample notes until it feels right, then turn that chat into the skill. write the skill description clearly because it decides when the skill runs.

- files: `viva/SKILL.md`, `viva/samples/` (3 fake notes), `viva/TESTING.md`. nothing else
- SKILL.md has a name and a description that triggers on /viva, "quiz me" or "ask me questions from this"
- first reply is a short greeting, what it read, the rules (`hint`, `skip`, `stop`) and Q1. it never asks anything else first, unless the notes are missing
- one question at a time, only from my notes, format like `Q2 of 5 · Heat engines · Level 3 (Apply)`, max about 35 words
- 5 levels (recall, explain, apply, analyse, evaluate). two right answers in a row go up a level, two misses go down
- partial answer: one follow-up on the exact gap, no lecture. wrong answer: one nudge, then move on. a bluff gets "give me a number or an example"
- default is 5 questions. options: `quick` (3), `deep` (10), and a persona (coach, professor, external examiner)
- score each question out of 1 (quarters), hints lower the max score
- at the end: score out of N, level reached, weak topics, "Revise page 14" style list, model answers for missed questions, and a 7 day revision plan
- samples are fake: thermo notes, DBMS notes (with one planted mistake to see if it flags it), photosynthesis notes
- TESTING.md has the done-when list and a with/without skill comparison table

1. starts correctly in a fresh session
2. works well on 3 different inputs
3. run the same task without the skill ("quiz me on this") and show what got better, with screenshots
4. fake notes only, no real documents
5. don't invent page numbers (only use a page if the page marker is really there) and don't reveal answers or the plan
6. no API, login or internet needed
7. if something goes wrong, give the agent a screenshot + SKILL.md and ask which line should have stopped it, fix that line and retest
8. keep my prompts in order in prompts.md and /teach me the skill until i can explain it

---

# PROMPT 7: SAME PAGE, NEW DESIGN (Project-17)

you are a front-end designer who knows HTML, CSS and accessibility, and can install and use a design skill.

this is project 17. build one plain page without any design skill, then redesign the same page with one. the words stay the same. my page is a fake college fest called **TECHNOVA 2026** (a tech and music fest, all content is made up). also write `design-notes.md` and take screenshots.

do it in 3 steps:
1. **step 1, without a skill:** build a simple page and save it as `before.html`. no design skill, no CSS
2. **step 2, add a design skill:** install one (Impeccable, or frontend-design / ui-ux-pro-max from skills.sh) and say in design-notes.md which one i used
3. **step 3, redesign:** use the skill on the same page and save it as `after.html`

- `before.html`: plain HTML, no CSS, exactly this text:
  - h1 "TECHNOVA 2026"
  - "Three days of robotics, code and music."
  - link "Register now" (goes to #register)
  - "Robotics · Hackathon · Music night"
  - h2 "Day by day", then h3 "Day 1: Robotics" with "Build and race line-following bots. Teams of up to three.", h3 "Day 2: Hackathon" with "Twelve hours to build something that works. Teams of up to four.", h3 "Day 3: Music night" with "Live bands and an open mic to close the fest."
  - h2 "Register" (id="register") with "Pick your event and register at the fest desk. Bring your college ID." and another "Register now" link
- how to make `after.html`: ask the skill to critique `before.html` first, write a short design plan, check it against the generic "AI page" defaults (purple gradient, centred cards, emoji icons), then fix the biggest problems one at a time
- `after.html`: one file, CSS inside, no JavaScript, system fonts only, no images or external files. words must stay identical to `before.html` and in the same order (it's fine to split "Day 1: Robotics" into a small "Day 1" label and a "Robotics" heading)
- 3 design changes:
  1. giant heavy wordmark instead of a default heading: "TECHNOVA" over "2026", Arial Black with a bold fallback, size set with clamp so it fills the top on every screen
  2. each day gets its own simple picture drawn in inline SVG: a race-track line with a dot for Robotics, code brackets and a cursor for Hackathon, equalizer bars for Music night. the bars rise once on page load (the only motion) and it's switched off for people with reduced motion
  3. clear structure and real buttons: the days sit side by side on a laptop and stack on a phone (auto-fit grid), "Register now" is a big coloured button (48px tall, good contrast) and it's repeated on a dark closing band
- colours: ink blue-black #0F1B2D, pale blue-grey paper #EEF1F6, cobalt #2B3BFF for the main action, amber #FFB400 for highlights, muted text #4A5568. no purple gradient
- also: viewport meta tag, text wraps, nothing scrolls sideways, visible focus outline on buttons, decorative SVGs marked aria-hidden, smooth scroll only when motion is allowed
- `design-notes.md`: page name, files, which design skill was used and the process (critique, plan, fixes), the 3 design changes with a reason why each one helps, other improvements, the done-when checklist, and an optional bonus idea (run a second design skill from skills.sh on before.html and compare it with after.html)
- `screenshots/`: before-phone, after-phone, before-desktop, after-desktop (phone is 390px wide, desktop is 1280px wide)

1. i must have both before.html and after.html
2. before.html is built with no design skill
3. the words in both files match word for word and in the same order (actually check it)
4. the redesign works on a phone with no sideways scroll
5. i can name 3 design changes and why each one helps
6. no libraries, no remote fonts, no emojis, works offline, fake content only
7. good contrast and a clear keyboard focus
8. don't say it's done until the screenshots are saved
9. keep every prompt i use in order in prompts.md

---

# PROMPT 8: CHAT SAVER (Project-12)

you are a chrome extension developer who knows manifest v3 and javascript.

this is project 12. make a chrome extension called **Chat Saver** that saves any AI chat as a clean PDF or Markdown file in one click. headings, lists, tables and code blocks should stay as they are, and nothing should be sent to any server.

start with Markdown on one chat site (find how the page separates my messages from the AI's), then add PDF, then the other sites.

- works on ChatGPT, Claude, Gemini, Perplexity, Copilot, DeepSeek and Grok
- popup with message counts (messages, code blocks, tables) and a list of the chat's messages with checkboxes
- save the full chat or only the messages i select
- buttons: Save as PDF, Save as Markdown (and a Copy Markdown button)
- long chats: scroll through the page to load every message, so 50+ messages save completely and in order
- code blocks keep their language, tables stay as tables
- file is named from the chat's title
- PDF opens in a print page so i can use Save as PDF, no libraries
- dark and light theme, forest green and brown colours
- footer: "Local processing only. No data leaves your device." and "Engineered by Akshay Srivatsava"
- README with install steps

1. works on at least 2 AI chat sites
2. a chat of 50+ messages saves completely
3. code from the saved file can be copied and still runs
4. tables stay tables
5. sends nothing to any server, no libraries or CDN
6. test with my own fake chats, not private ones, and run `node --check` on the JS files
7. a friend can install it using only my README

---


