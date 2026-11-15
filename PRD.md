# Siriously landing page and identity PRD

Nov 15, 2026 · Hari

## Summary
Build a one-page landing site for Siriously using the H2 Warm field layout and the A3 Tilted arc logo. Both were picked from the design canvas ("Siriously — landing page directions") on 15 November 2026.
Siriously is hands-free voice control for the Mac, built by Hari and Henrik for a local AI hackathon. It runs entirely on the user's machine.

## Decision
| Choice | |
|---|---|
| Layout | H2 Warm field: a full-width peach block holding a voiceprint, with very little else on the page |
| Logo | A3 Tilted arc: two eyes under one thick arc, raised on the right |
| Accent | Soft warm peach, used as a field of colour and never for text |
| Typeface | Geist, in two weights |
| Action | One: Watch the demo |

## Goals
- Say what it is in one line: voice control for the Mac that runs on the Mac.
- Give one action, Watch the demo, and nothing that competes with it.
- Look like a real product: unique, premium, not templated or AI-looking.
- Carry the joke in the name without explaining it.

## Non-goals
No waitlist, sign-up, pricing, download, docs or blog. Not the captions UI. Nothing that borrows the look of Apple's Siri.

## Logo: A3 Tilted arc
| Part | Spec |
|---|---|
| Arc | Radius 30 over the top from (22, 46) to (78, 46), stroke 10, round ends, rotated 12° anticlockwise about (50, 46) |
| Eyes | Two circles r 8 at (34, 68) and (66, 68) |
| Tile | Rounded square rx 23, app icon and favicon only |

Usage: app icon, favicon, social image = ink mark on the peach tile. Nav and footer = ink mark alone on white, 26px high. Dark grounds = white mark, no tile. Clear space one eye-width; never below 16px. Do not recolour arc and eyes separately, add a mouth, or change the tilt.

## Colour
| Name | Hex | Used for |
|---|---|---|
| Ink | #0A0A0A | Text, voiceprint bars, logo, button |
| White | #FFFFFF | Page ground, button text |
| Peach field | #F7CDB0 | The voiceprint block |
| Logo peach | #F9D9C2 | Logo tile (superseded: one peach, see Resolved) |
| Warm grey | #857A70 | Second half of large headlines only |
| Brown grey | #5F564E | Body text, nav links, footer |
| Deep brown | #3A2A1E | Word labels on the peach field |
| Hairline | #DCDCD8 | Rules between statements |

## Type
Geist only, weights 400 and 500.
| Role | Size | Weight | Notes |
|---|---|---|---|
| Headline | 34–46px fluid | 500 | tracking -0.03em, lh 1.06 |
| Statements | 30–46px fluid | 500 | same tracking, lh 1.08 |
| Body | 15px | 400 | lh 1.5 |
| Nav | 12px | 400 | capitals, tracking 0.12em |
| Word labels | 13px | 400 | under the voiceprint |
| Footer | 14px | 400 | |

## Page structure and copy
1. Nav: A3 mark left (links to top); DEMO, HOW IT WORKS, PRIVACY in the middle; WATCH on the right.
2. Voiceprint block: full-width peach field, voiceprint, words open / Slack / and / say / the / build / is / up.
3. Intro: headline "Siriously." in ink then "Voice control for the Mac that does what you said." in warm grey; paragraph "Say what you want in plain words and Siriously works your apps for you. It runs entirely on your own machine."; button "Watch the demo". Headline left, paragraph + button right, bottom-aligned.
4. Statements, hairline-separated: "Runs on your Mac. / Nothing you say is uploaded." · "Works in any app. / Not just one it was built for." · "Shows what it heard. / And who said it."
5. Footer: "Made by Hari and Henrik at [HACKATHON NAME]" left, "Siriously" right.

Layout: margins 16–24px fluid, no max-width container. 40px above the peach block, 72px to the intro, 88px below the intro, 96px below the statements. Button: ink, white text, 44px high, 8px radius, 15px medium. Statements: 28px padding above and below each hairline.
Links: DEMO, WATCH and the button go to the demo. HOW IT WORKS and PRIVACY scroll to the statements.

## The voiceprint
One inline SVG, viewBox 1200×520 stretched to block width; 72 bars, 9 wide, rounded, ~16.7 apart, centred; eight bursts, Slack and build tallest. Ink on peach. Height 260–520px (36vw). Block padding 24–56px, square corners. Labels 13px #3A2A1E spread edge to edge.
Copy the SVG from the H2 Warm field artboard; do not redraw. It is an illustration, not a recording. Version one is static.

## Responsive, accessibility and motion
360px phone to projector; nothing clipped, no horizontal scroll. Intro stacks below ~900px. Nav links wrap under the mark below ~600px (no menu button). Voiceprint never below 260px; word labels stay on one row.
Body and nav text ≥ 4.5:1. Warm grey (~4.2:1) only at ≥ 30px. Every link and the button ≥ 44px high, keyboard reachable, visible 2px ink focus ring. Voiceprint label "Voiceprint of the sentence: open Slack and say the build is up"; word row hidden from screen readers. One h1. Statements are paragraphs.
No motion required. Hover changes colour only.

## Build and delivery
One static HTML file with inline CSS, no framework, no build step.
Files: index.html, logo-mark.svg, logo-mark-white.svg, app-icon.svg + 512px PNG, favicon (32px, mark on tile), social image 1200×630 (peach field, voiceprint, mark). Ship Geist with the page if it must work offline.

## Resolved during build (15 Nov 2026)
- Hackathon name: "the Cornell Local AI Hackathon" (from the siriously repo README).
- One peach: #F7CDB0 for both the field and the logo tile.
- Offline: yes (the siriously PRD says the demo must run with wifi off). Geist ships in `fonts/`.
- "Seriously? / Siriously.": not used (H2 does not include it).
- GitHub link featured (Hari, 15 Nov): GITHUB as a fourth nav link, and "View the code on GitHub" as a quiet underlined text link beside the button. Both go to https://github.com/Henrik66/siriously. The button stays the only filled action.

- Footer credit removed (Hari, 15 Nov). Footer is "Siriously" alone, on the right.
- Demo (Hari, 15 Nov): the video is https://www.youtube.com/watch?v=ZjN_ducezP0. DEMO, WATCH and the button open it with sound. Beside the headline, a small silent product loop (demo-loop.webm, 13 s, 1 MB, rendered from the repo's demo-video scenes, so no YouTube overlay and it works offline) plays while it is on screen and links to the same video. With reduced motion it shows its poster and never plays. A pinned corner player was tried and dropped, because the compact page left it covering text at nearly every scroll position.
- Overrides the "no mention of Apple's assistant" voice rule (Hari, 15 Nov): a "Seriously? / Siriously." pair contrasts Apple's Voice Control ("Show numbers. Click 14. Click 3.") with one plain sentence, followed by a short accessibility note. It still does not mention Siri.
- A fourth claim for accessibility: "Works without your hands. Say “Siriously” and keep talking."
- Bottom half redesigned (Hari, 15 Nov): the Seriously?/Siriously. pair as two 20px rows, each with a small voiceprint (halting bursts for Voice Control, the hero sentence on peach for Siriously), with the accessibility note beside them. The four claims sit in one row at 15px, the footer is the mark plus "Siriously" on the left, and everything shares one four-column grid. The bottom half is about half its old height.
- Motion (Hari, 15 Nov, overrides "no motion"): the voiceprint plays in left to right over 1.2 s on load, with words fading in as their bursts arrive; the bottom half reveals once on scroll; the footer mark blinks on hover. Transform and opacity only. All of it is off with reduced motion, and all content shows without JS.

- Carbon counter (Hari, 15 Nov): a slim row under the claims counts the data-center CO₂e not emitted while the visitor is on the page. It assumes one command every 20 s, each counted at Google's August 2025 median for a Gemini text prompt (about 0.24 Wh, 0.03 g CO₂e), so 1.5 mg a second. It is labelled "An estimate, not a measurement" and notes that the Mac still uses power. It pauses off screen and in hidden tabs, has a pause button (WCAG 2.2.2), steps only every ~10 s with reduced motion, and shows a static per-minute line without JS.

## Still open
- Hosting and domain (og:image is relative until there is one).
- Projector body size, go-live date.
