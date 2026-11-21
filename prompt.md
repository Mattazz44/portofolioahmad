# ROLE & OBJECTIVE
Act as a Senior Creative Front-End Engineer & UI/UX Designer. Refactor and fix the portfolio website (`./index.html`) inside this `website_porto` workspace using **semantic HTML5, Tailwind CSS (via CDN), and Vanilla JavaScript**.

# WORKSPACE FILE STRUCTURE & ASSET MAPPING
Strictly use these exact relative paths:
- **Output File:** `./index.html`
- **Profile Photo Asset:** `./foto/foto.png`
- **Downloadable Resume PDF:** `./document/CV_Ahmad_Fauzi_Hasbi_Nasution_Front-End_Developer.pdf` (Inspect `./document/` to confirm exact filename)

---

# CRITICAL FIXES & FLOW ARCHITECTURE (READ CAREFULLY)

## 1. STRICT PAGE FLOW & STATE LOCKING (Arcade Intro -> Main Portfolio)
- **Initial State (On Page Load):** ONLY the **Green Arcade Cabinet Intro Screen** (`#arcade-intro`) must be visible (`100vw`, `100vh`, `overflow: hidden`). The main portfolio wrapper (`#main-portfolio`) MUST be completely hidden (`display: none` or `hidden`) and `body` scrolling MUST be locked (`overflow-y: hidden`) until the user enters.
- **Triggering Entry:** Clicking the green CRT screen, the `→` arrow button, `► BOOT PORTFOLIO`, `SKIP INTRO`, or pressing `Enter`/`Space` must:
  1. Play a cute 8-bit startup chime (Web Audio API).
  2. Trigger a crisp CRT power-on flash transition.
  3. Hide `#arcade-intro`, reveal `#main-portfolio`, unlock `body` vertical scrolling, and **automatically scroll smoothly to the very top (`window.scrollTo(0, 0)`) of the Hero Landing Page**.
- **Return to Arcade Button:** Clicking `ARCADE CABINET` in the top-right of the Hero section reverses the transition back to `#arcade-intro` and locks scrolling again.

## 2. CLEAN, NON-OVERLAPPING HERO SECTION LAYOUT
Fix the overlapping text bug in the Hero Section (`100vh` minimum height, flex column layout with clean vertical spacing `gap-6`):
- **Top Bar:** Flex row with `BOGOR, ID // GPA 3.36` on the left and `ARCADE CABINET` + a `SOUND: ON/OFF` toggle button on the right.
- **Title & Subtitle (NO OVERLAP):**
  - Render the giant pixel title **`FAUZI.DEV`** cleanly at the top with generous line-height.
  - Place the yellow pixel-bordered badge (*"Front-End Developer & UI/UX Designer — Building accessible, high-craft web experiences."*) **cleanly BELOW `FAUZI.DEV`** (do NOT overlap or cover the letters of `FAUZI.DEV`).
- **Interactive Animated Mascot (Centerpiece):**
  - Place the custom CSS/SVG pixel Tamagotchi mascot cleanly below the yellow badge.
  - **Idle Animation:** Gentle floating/bobbing animation (`@keyframes float`) and occasional eye blinking.
  - **Interactive Emotion System (On Click/Tap):** Every time the user clicks the mascot, cycle through **5 distinct cute pixel emotions** with a floating pixel speech bubble above its head AND a matching cute 8-bit sound effect:
    1. **Happy (`^‿^`):** Jumps up, pink blush cheeks appear, speech bubble says `"YAY! HI RECRUITER! ♡"` + cheerful high-pitched 8-bit arpeggio.
    2. **Love (`♥‿♥`):** Heart eyes + floating pixel hearts, speech bubble says `"HIRE FAUZI 2027! ★"` + cute double-chirp coin sound.
    3. **Surprised (`O_O`):** Shakes briefly with `!` mark, speech bubble says `"WHOA! SO FAST!"` + bouncy pitch-bend blip.
    4. **Cool (`■_■`):** Pixel sunglasses drop onto its eyes, speech bubble says `"100% ANTI-SLOP!"` + retro power-up synth riff.
    5. **Sleepy/Dizzy (`@_@`):** Wobbly animation, speech bubble says `"NEED MORE COFFEE..."` + soft descending boop.
- **Action Buttons & Horizon Nav:**
  - Below the mascot: `TAP MASCOT FOR EMOTIONS // INTERNSHIP READY FEB – JUNE 2027`
  - Clean horizontal button group: **`► PRESS START`** and **`↓ DOWNLOAD CV`**.
  - Bottom of Hero: Stepped black pixel skyline divider with the centered hot-pink (`#FF006E`) navigation bar (`[ ABOUT ME ]`, `[ PROJECTS ]`, `[ UI/UX ]`, `[ CONTACT ]`).

## 3. WEB AUDIO API CUTE 8-BIT SOUND ENGINE (ZERO EXTERNAL AUDIO FILES)
Build a lightweight Vanilla JS `SoundFX` synthesizer using `window.AudioContext`:
- **Cute Mascot Sounds:** Play distinct cute, bubbly square/triangle-wave melodies depending on the mascot's current emotion.
- **UI Micro-Interactions:** Subtle cute short "blip" (`600Hz -> 900Hz`, 50ms) when hovering/clicking buttons, arcade joysticks, or navigation links.
- **Mute Toggle:** Include a working pixel speaker toggle button (`SFX: ON` / `SFX: OFF`) in the top bar. Safely initialize `AudioContext` on the first user click so browser autoplay policies never throw errors.

---

# 4. PORTFOLIO CONTENT SECTIONS (Dark Void `#0D0D0D` + Pixel Stars)

## Section 1: "WHO AM I?" (About Me)
- **Left Column:** Render `<img src="./foto/foto.png" alt="Ahmad Fauzi Hasbi Nasution" />` inside a framed retro Tamagotchi/pixel-art card with a pixel Earth graphic at the bottom corner.
- **Right Column:** Monospace bio with `#FF006E` hot-pink highlight pills:
  - **Ahmad Fauzi Hasbi Nasution** — **Front-End Developer** & **Software Engineering Technology (D4)** student at **IPB University** (GPA 3.36/4.00), Bogor, Indonesia.
  - Combines **UI/UX Design** with modern front-end engineering (**React.js, Vite, Tailwind CSS, Bootstrap, PWA**). **IFEST 2026 Hackathon Finalist** & **Gemini Certified Student**.
  - **Available for Internship: February – June 2027 (Onsite/Hybrid)**.

## Section 2: TECHNICAL SKILLS (Arcade Inventory Cards)
- **Front-End:** React.js, Vite, HTML5, CSS3, JavaScript (Basic), Tailwind CSS, Bootstrap 5, Responsive Design, Progressive Web Apps (PWA).
- **UI/UX Design:** User Flows, Wireframing, High-Fidelity Mockups, Prototyping, Design Systems, Accessibility.
- **Tools:** Git, GitHub, Figma, FigJam.
- **Languages & Certs:** Indonesian (Native), English (Intermediate), Gemini Certified Student (Google for Education, 2026–2029).

## Section 3: PROJECT EXPERIENCE
1. **Sabah Bogor — Progressive Web App for Tourists** *(Front-End Developer, Team of 5 | 2026)* — React.js, Vite, React-Leaflet, OSRM Routing API, HTML5 Geolocation API, Custom Hooks & LocalStorage. GitHub: `https://github.com`
2. **Plant Breeding & Seed Technology Study Program Website** *(Front-End Developer, Team of 4 | 2025)* — Multi-page academic site with HTML, Tailwind CSS, custom font theming. GitHub: `https://github.com`
3. **Porsche Fan Website** *(Personal Project | 2026)* — 13-page responsive showcase built with HTML, CSS, JavaScript, and Bootstrap 5. GitHub: `https://github.com`

## Section 4: UI/UX DESIGN & HACKATHON ACHIEVEMENTS
1. **SUDEPI (Suara Deteksi Rupiah)** — *IFEST 2026 Hackathon Finalist (50+ teams) | UI/UX Designer (2026)*. Figma: `https://figma.com`
2. **Portal 7 International Competition** — *Semifinalist | UI/UX Designer (2025)*. Figma: `https://figma.com`
3. **Cocokin** — *Hackathon | UI Designer (2026)*. Figma: `https://figma.com`

## Section 5: FOOTER / "INSERT COIN TO CONNECT"
- Clickable pixel buttons for:
  - Download CV PDF (`./document/CV_Ahmad_Fauzi_Hasbi_Nasution_Front-End_Developer.pdf`)
  - Email: `hasbinasutionahmadfauzi@gmail.com`
  - Phone/WhatsApp: `+62 853-7281-7753`
  - LinkedIn: `https://linkedin.com`
  - GitHub: `https://github.com`
