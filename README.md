<div align="center">

# 🎬 Netflix Landing Page Clone

**A responsive streaming-service landing page built with pure HTML and CSS, with no frameworks and no JavaScript**

</div>

> ⚠️ **Disclaimer:** This is an educational practice project and is **not affiliated with Netflix**. The name, layout, and design are used only as inspiration for learning front-end development. Netflix's logo and hosted media are their property. Don't present this project as a real product, and check the license of any asset before publishing it.

---

## 📖 About This Project

This project recreates the landing page of a video streaming service. It is a single page with a hero banner, four feature sections, an FAQ list, and a footer.

The goal was to practice the CSS I have been learning (positioning, `z-index`, Flexbox, Grid, media queries, transitions, filters, and CSS math functions) on one realistic page instead of in small isolated demos.

---

## 📑 Table of Contents

1. [Features](#-features)
2. [Tech Stack](#-tech-stack)
3. [Project Structure](#-project-structure)
4. [Page Walkthrough](#-page-walkthrough)
5. [How the Layering Works](#-how-the-layering-works)
6. [The TV and Video Trick](#-the-tv-and-video-trick)
7. [CSS Concepts Used](#-css-concepts-used)
8. [Responsive Design](#-responsive-design)
9. [Design Tokens](#-design-tokens)
10. [Known Issues & Fixes](#-known-issues--fixes)
11. [How to Run](#-how-to-run)
12. [What I Learned](#-what-i-learned)
13. [Roadmap](#-roadmap)

---

## ✨ Features

<table>
  <tr>
    <th>Feature</th>
    <th>Description</th>
    <th>Built with</th>
  </tr>
  <tr>
    <td>🖼️ <b>Dimmed hero banner</b></td>
    <td>A background photo with a dark overlay so white text stays readable.</td>
    <td><code>background-image</code>, <code>position: absolute</code>, <code>opacity</code></td>
  </tr>
  <tr>
    <td>🧭 <b>Centered navbar</b></td>
    <td>Logo on the left, language and Sign In buttons on the right.</td>
    <td>Flexbox, <code>space-between</code></td>
  </tr>
  <tr>
    <td>📧 <b>Email sign-up bar</b></td>
    <td>An input and a red "Get Started" button side by side.</td>
    <td>Flexbox</td>
  </tr>
  <tr>
    <td>📺 <b>Video inside a TV frame</b></td>
    <td>A muted, looping video plays behind a TV image so it looks like it's on the screen.</td>
    <td><code>position</code> + <code>z-index</code> layering</td>
  </tr>
  <tr>
    <td>↔️ <b>Alternating sections</b></td>
    <td>Text and image swap sides from one section to the next.</td>
    <td>Flexbox, HTML source order</td>
  </tr>
  <tr>
    <td>❓ <b>FAQ boxes</b></td>
    <td>Four dark boxes that lighten on hover, each with a "+" icon.</td>
    <td><code>transition</code>, <code>:hover</code>, <code>filter: invert()</code></td>
  </tr>
  <tr>
    <td>🦶 <b>Link footer</b></td>
    <td>Sixteen links in four columns that collapse to two.</td>
    <td>CSS Grid</td>
  </tr>
  <tr>
    <td>📱 <b>Responsive layout</b></td>
    <td>Smaller type, stacked sections, and a stacked sign-up form on narrower screens.</td>
    <td>Media query at <code>1300px</code></td>
  </tr>
</table>

---

## 🛠️ Tech Stack

<table>
  <tr>
    <th>Layer</th>
    <th>Technology</th>
    <th>Used for</th>
  </tr>
  <tr>
    <td>Structure</td>
    <td>HTML5</td>
    <td>Sections, nav, footer, <code>&lt;video&gt;</code>, inline <code>&lt;svg&gt;</code></td>
  </tr>
  <tr>
    <td>Styling</td>
    <td>CSS3</td>
    <td>Positioning, Flexbox, Grid, transitions, filters, <code>max()</code>, <code>calc()</code></td>
  </tr>
  <tr>
    <td>Typography</td>
    <td>Google Fonts</td>
    <td>Poppins (300, 400, 700) and Martel Sans (600)</td>
  </tr>
  <tr>
    <td>JavaScript</td>
    <td>None</td>
    <td>Everything here is done with HTML and CSS</td>
  </tr>
</table>

---

## 📂 Project Structure

```
netflix-clone/
│
├── index.html
├── style.css
├── favicon.ico
│
└── assets/
    ├── images/
    │   ├── bg.jpg          # hero background photo
    │   └── logo.svg        # logo used in the navbar
    │
    └── videos/
        └── video1.m4v      # local video (currently unused)
```

<table>
  <tr>
    <th>File</th>
    <th>Purpose</th>
  </tr>
  <tr>
    <td><code>index.html</code></td>
    <td>The whole page: hero, four feature sections, FAQ, and footer.</td>
  </tr>
  <tr>
    <td><code>style.css</code></td>
    <td>All styling, including the responsive rules.</td>
  </tr>
  <tr>
    <td><code>assets/images/bg.jpg</code></td>
    <td>Hero background, used as a CSS <code>background-image</code>.</td>
  </tr>
  <tr>
    <td><code>assets/images/logo.svg</code></td>
    <td>Navbar logo.</td>
  </tr>
  <tr>
    <td><code>assets/videos/video1.m4v</code></td>
    <td>A local video. The page currently uses hosted videos instead (see <a href="#-known-issues--fixes">Known Issues</a>).</td>
  </tr>
  <tr>
    <td><code>favicon.ico</code></td>
    <td>Tab icon. Add a <code>&lt;link rel="icon"&gt;</code> tag so every server finds it.</td>
  </tr>
</table>

---

## 🧭 Page Walkthrough

<table>
  <tr>
    <th>#</th>
    <th>Section</th>
    <th>Contents</th>
    <th>Layout</th>
  </tr>
  <tr>
    <td align="center">1</td>
    <td><b>Hero</b> (<code>.main</code>)</td>
    <td>Logo, English and Sign In buttons, the headline "Enjoy big movies, hit series and more from ₹ 149.", a subtitle, a prompt, and the email form</td>
    <td>Background image, absolute overlay, Flexbox</td>
  </tr>
  <tr>
    <td align="center">2</td>
    <td><b>Enjoy on your TV</b></td>
    <td>Text on the left, TV frame with a video on the right</td>
    <td>Flexbox row</td>
  </tr>
  <tr>
    <td align="center">3</td>
    <td><b>Download your shows</b></td>
    <td>Phone image on the left, text on the right</td>
    <td>Flexbox row (image first in the HTML)</td>
  </tr>
  <tr>
    <td align="center">4</td>
    <td><b>Watch everywhere</b></td>
    <td>Text on the left, TV frame with a video on the right</td>
    <td>Flexbox row</td>
  </tr>
  <tr>
    <td align="center">5</td>
    <td><b>Create profiles for kids</b></td>
    <td>Image on the left, text on the right</td>
    <td>Flexbox row (image first in the HTML)</td>
  </tr>
  <tr>
    <td align="center">6</td>
    <td><b>FAQ</b></td>
    <td>"What is Netflix", "How much does Netflix cost?", "What can I watch on Netflix?", "Where can I watch?"</td>
    <td>Stacked flex boxes at 60vw</td>
  </tr>
  <tr>
    <td align="center">7</td>
    <td><b>Footer</b></td>
    <td>A phone-number line and 16 links</td>
    <td>CSS Grid, 4 columns</td>
  </tr>
</table>

Between sections, a thin 7px gray bar (`.separation`) acts as a divider.

### 🔀 How Sections Alternate

There are no special CSS rules for "text left" or "image left". The order is decided only by the **order of the elements in the HTML**:

<table>
  <tr>
    <th>Section</th>
    <th>HTML order</th>
    <th>Result</th>
  </tr>
  <tr>
    <td>Enjoy on your TV, Watch everywhere</td>
    <td>text, then image</td>
    <td>Text on the left</td>
  </tr>
  <tr>
    <td>Download your shows, Kids profiles</td>
    <td>image, then text</td>
    <td>Image on the left</td>
  </tr>
</table>

---

## 🥞 How the Layering Works

The hero stacks three layers. The tricky part is getting the navbar to appear **above** the dark overlay.

<table>
  <tr>
    <th>Layer (bottom to top)</th>
    <th>Element</th>
    <th>How it's placed</th>
  </tr>
  <tr>
    <td>1️⃣ Photo</td>
    <td><code>.main</code></td>
    <td><code>background-image</code> with <code>position: relative</code></td>
  </tr>
  <tr>
    <td>2️⃣ Dark overlay</td>
    <td><code>.main .box</code></td>
    <td><code>position: absolute; top: 0;</code> black at <code>opacity: 0.69</code></td>
  </tr>
  <tr>
    <td>3️⃣ Content</td>
    <td><code>.hero</code></td>
    <td><code>position: relative</code>, so it paints above the overlay (later in the HTML)</td>
  </tr>
  <tr>
    <td>3️⃣ Nav logo and buttons</td>
    <td><code>nav img</code>, <code>nav button</code></td>
    <td><code>position: relative; z-index: 10;</code> to lift them above the overlay</td>
  </tr>
</table>

### 🧠 Why the Nav Needs `z-index`

<table>
  <tr>
    <td>1️⃣</td>
    <td>The <code>&lt;nav&gt;</code> itself is <b>not positioned</b>. Positioned elements paint on top of non-positioned ones.</td>
  </tr>
  <tr>
    <td>2️⃣</td>
    <td>The overlay <code>.box</code> is <b>absolutely positioned</b>, so it paints over the nav and would hide the logo and buttons behind a dark layer (and block clicks on them).</td>
  </tr>
  <tr>
    <td>3️⃣</td>
    <td>Giving the logo and buttons <code>position: relative; z-index: 10</code> lifts them back above the overlay. The <code>.hero</code> needs only <code>position: relative</code>, because it comes later in the HTML than the overlay.</td>
  </tr>
</table>

```css
.main {
  background-image: url("assets/images/bg.jpg");
  background-position: center center;
  background-size: max(1200px, 100vw);
  background-repeat: no-repeat;
  height: 644px;
  position: relative;          /* anchor for the overlay */
}

.main .box {                    /* the dark overlay */
  height: 644px;
  width: 100%;
  opacity: 0.69;
  position: absolute;
  top: 0;
  background-color: black;
}

nav img,
nav button {
  position: relative;
  z-index: 10;                  /* above the overlay */
}
```

---

## 📺 The TV and Video Trick

The feature sections make a video look like it's playing inside a TV, using only two stacked elements.

```html
<div class="secImg">
  <img src="...tv.png" alt="">          <!-- the TV frame (screen area is transparent) -->
  <video src="...video.m4v" autoplay loop muted></video>
</div>
```

```css
.secImg {
  position: relative;            /* anchor for the video */
}

.secImg img {
  width: 555px;
  position: relative;
  z-index: 10;                   /* frame sits ON TOP */
}

.secImg video {
  position: absolute;
  top: 51px;                     /* moves the video down onto the screen */
  right: 0;
  width: 555px;                  /* same width as the frame */
}
```

<table>
  <tr>
    <th>Step</th>
    <th>What happens</th>
  </tr>
  <tr>
    <td>1️⃣</td>
    <td>The TV image has a <b>transparent screen area</b>, so anything behind it shows through.</td>
  </tr>
  <tr>
    <td>2️⃣</td>
    <td>The video is positioned <code>absolute</code> inside the <code>relative</code> container, so it sits behind the image and doesn't push the layout.</td>
  </tr>
  <tr>
    <td>3️⃣</td>
    <td>The image has <code>z-index: 10</code>, so the frame draws over the video and hides its edges.</td>
  </tr>
  <tr>
    <td>4️⃣</td>
    <td><code>autoplay loop muted</code> make it play silently on repeat. Browsers only allow autoplay when the video is <b>muted</b>.</td>
  </tr>
</table>

---

## 🧠 CSS Concepts Used

<table>
  <tr>
    <th>Concept</th>
    <th>Where it's used</th>
  </tr>
  <tr>
    <td>CSS reset</td>
    <td><code>* { padding: 0; margin: 0; }</code></td>
  </tr>
  <tr>
    <td><code>@import</code> for web fonts</td>
    <td>Poppins and Martel Sans from Google Fonts</td>
  </tr>
  <tr>
    <td><code>background-size</code> with <code>max()</code></td>
    <td><code>max(1200px, 100vw)</code> keeps the hero image from shrinking below 1200px</td>
  </tr>
  <tr>
    <td><code>calc()</code></td>
    <td><code>height: calc(100% - 100px)</code> fills the hero minus the 100px navbar</td>
  </tr>
  <tr>
    <td><code>position</code> (<code>relative</code>, <code>absolute</code>)</td>
    <td>Hero overlay, video over TV, nav layering</td>
  </tr>
  <tr>
    <td><code>z-index</code> and stacking order</td>
    <td>Nav above overlay, TV frame above video, dividers on top</td>
  </tr>
  <tr>
    <td>Flexbox</td>
    <td>Navbar, hero, button row, text-and-image sections, FAQ boxes, footer columns</td>
  </tr>
  <tr>
    <td><code>flex-wrap: wrap</code></td>
    <td>Stacks the feature sections on narrow screens</td>
  </tr>
  <tr>
    <td>CSS Grid</td>
    <td>Footer: <code>repeat(4)</code> columns, changed to 2 columns by a media query</td>
  </tr>
  <tr>
    <td><code>:nth-child()</code> with the child combinator</td>
    <td><code>.hero &gt; :nth-child(1)</code> styles the three hero lines by position</td>
  </tr>
  <tr>
    <td>Descendant and child selectors</td>
    <td><code>section.first &gt; div</code>, <code>.main input</code>, <code>.faqbox svg</code></td>
  </tr>
  <tr>
    <td>Transitions and <code>:hover</code></td>
    <td>FAQ boxes lighten from <code>#2d2d2d</code> to <code>#414141</code></td>
  </tr>
  <tr>
    <td><code>filter: invert(1)</code></td>
    <td>Recolors the SVG "+" icons</td>
  </tr>
  <tr>
    <td>Inline SVG</td>
    <td>The "+" icon in each FAQ box</td>
  </tr>
  <tr>
    <td>Semi-transparent colors (<code>rgba</code>)</td>
    <td>Input background and border, translucent buttons</td>
  </tr>
  <tr>
    <td>Viewport units</td>
    <td><code>max-width: 60vw</code>, <code>70vw</code>, <code>90vw</code> for centered content</td>
  </tr>
  <tr>
    <td>Centering with <code>margin: auto</code></td>
    <td>Navbar, sections, FAQ boxes, footer</td>
  </tr>
  <tr>
    <td>Media queries</td>
    <td>One breakpoint at <code>1300px</code></td>
  </tr>
</table>

### 🔬 Selector Spotlight: Styling by Position

Instead of adding a class to every line in the hero, the CSS targets each child by its position:

```css
.hero > :nth-child(1) { font-size: 48px; font-weight: bolder; }  /* headline  */
.hero > :nth-child(2) { font-size: 24px; font-weight: 400;    }  /* subtitle  */
.hero > :nth-child(3) { font-size: 20px; font-weight: 400;    }  /* prompt    */
```

The same idea styles the feature sections: the first child of each text block becomes a large heading and the second becomes a smaller description.

```css
section.first > div :nth-child(1) { font-size: 48px; font-weight: bolder; }
section.first > div :nth-child(2) { font-size: 24px; }
```

> 💡 This is compact, but it breaks if the HTML order changes. For larger projects, named classes are safer.

---

## 📱 Responsive Design

<table>
  <tr>
    <th>Element</th>
    <th>Above 1300px</th>
    <th>1300px and below</th>
  </tr>
  <tr>
    <td>Navbar width</td>
    <td align="center"><code>60vw</code></td>
    <td align="center"><code>90vw</code></td>
  </tr>
  <tr>
    <td>Hero headline</td>
    <td align="center"><code>48px</code></td>
    <td align="center"><code>32px</code></td>
  </tr>
  <tr>
    <td>Hero subtitle and prompt</td>
    <td align="center"><code>24px</code> / <code>20px</code></td>
    <td align="center"><code>18px</code> / <code>18px</code></td>
  </tr>
  <tr>
    <td>Email form</td>
    <td align="center">Input and button side by side</td>
    <td align="center">Stacked in a column</td>
  </tr>
  <tr>
    <td>Feature sections</td>
    <td align="center">Text and image side by side</td>
    <td align="center">Wrapped: stacked vertically (<code>flex-wrap</code>)</td>
  </tr>
  <tr>
    <td>TV image and video</td>
    <td align="center"><code>555px</code></td>
    <td align="center"><code>305px</code></td>
  </tr>
  <tr>
    <td>FAQ heading</td>
    <td align="center"><code>48px</code></td>
    <td align="center"><code>32px</code></td>
  </tr>
  <tr>
    <td>Footer width and padding</td>
    <td align="center"><code>60vw</code>, <code>60px</code></td>
    <td align="center"><code>90vw</code>, <code>75px 0</code></td>
  </tr>
  <tr>
    <td>Footer columns</td>
    <td align="center">4 columns</td>
    <td align="center">2 columns with a <code>25px</code> gap, items centered</td>
  </tr>
</table>

---

## 🎨 Design Tokens

<table>
  <tr>
    <th>Use</th>
    <th>Value</th>
  </tr>
  <tr>
    <td>Page background</td>
    <td><code>black</code></td>
  </tr>
  <tr>
    <td>Hero overlay</td>
    <td><code>black</code> at <code>opacity: 0.69</code></td>
  </tr>
  <tr>
    <td>Primary button</td>
    <td><code>red</code></td>
  </tr>
  <tr>
    <td>Divider bars</td>
    <td><code>rgb(46, 44, 44)</code>, <code>7px</code> tall</td>
  </tr>
  <tr>
    <td>FAQ box</td>
    <td><code>#2d2d2d</code>, hover <code>#414141</code></td>
  </tr>
  <tr>
    <td>Input background</td>
    <td><code>rgba(23, 23, 23, 0.7)</code></td>
  </tr>
  <tr>
    <td>Input border</td>
    <td><code>rgba(246, 238, 238, 0.5)</code></td>
  </tr>
  <tr>
    <td>Body font</td>
    <td>Poppins (300, 400, 700)</td>
  </tr>
  <tr>
    <td>Hero font (intended)</td>
    <td>Martel Sans (600). See <a href="#-known-issues--fixes">Known Issues</a></td>
  </tr>
</table>

> 💡 These values repeat in several places. Moving them into CSS variables (`:root { --red: red; --faq-bg: #2d2d2d; }`) would let the whole theme change from one spot.

---

## 🐛 Known Issues & Fixes

Being honest about what isn't perfect yet is part of learning. Here is what I found while reviewing the code, with a fix for each.

<details>
<summary><b>1. 🔤 Martel Sans never shows up</b></summary>

<br>

`* { font-family: 'Poppins' }` sets the font **directly on every element**. That overrides inheritance, so `font-family: 'Martel Sans'` on `.hero` never reaches the spans inside it (only the first child is set again, to Poppins). Martel Sans is loaded but never used.

**Fix:** put the base font on `body`, so elements inherit it and can still override it:

```css
body {
  background-color: black;
  font-family: 'Poppins', sans-serif;
}

.hero {
  font-family: 'Martel Sans', sans-serif;   /* now children inherit this */
}
```

</details>

<details>
<summary><b>2. 📺 The video drifts out of the TV on small screens</b></summary>

<br>

The video's `top: 51px` is a fixed offset, but under `1300px` the TV image shrinks from `555px` to `305px`. The video then sits too low on the screen.

**Fix:** drive both sizes from one variable, so the offset scales with the image (51 ÷ 555 ≈ 0.092):

```css
.secImg { --tv: 555px; position: relative; }

.secImg img   { width: var(--tv); position: relative; z-index: 10; }
.secImg video { width: var(--tv); position: absolute; right: 0;
                top: calc(var(--tv) * 0.092); }

@media screen and (max-width: 1300px) {
  .secImg { --tv: 305px; }
}
```

</details>

<details>
<summary><b>3. ❓ The FAQ "+" boxes don't do anything</b></summary>

<br>

They look like an accordion but have no behavior. The built-in `<details>` and `<summary>` elements give you an accordion with **no JavaScript**:

```html
<details class="faq-item">
  <summary>What is Netflix?</summary>
  <p>Netflix is a streaming service that offers a wide variety of shows and movies.</p>
</details>
```

```css
.faq-item {
  background-color: #2d2d2d;
  max-width: 60vw;
  margin: 34px auto;
  padding: 24px;
  font-size: 24px;
  transition: background-color 0.3s ease;
}
.faq-item:hover { background-color: #414141; }
.faq-item summary { cursor: pointer; }
.faq-item p { margin-top: 16px; font-size: 18px; }
```

Also:
- `transition: all 1s` feels slow for a hover. `0.3s` is more typical.
- "NetFlix" has a capital F typo.
- The "+" SVG uses `stroke="#141B34"` and then `filter: invert(1)`. Setting `stroke="white"` directly is simpler and needs no filter.

</details>

<details>
<summary><b>4. 🦶 Footer and CSS cleanup</b></summary>

<br>

<table>
  <tr>
    <th>Issue</th>
    <th>Fix</th>
  </tr>
  <tr>
    <td>"Speed Test" and "Legal Notices" each appear twice (columns 2 and 4)</td>
    <td>Remove the duplicates or replace them with real links.</td>
  </tr>
  <tr>
    <td>Every link points to <code>href="faq"</code></td>
    <td>Use <code>href="#"</code> as a placeholder, or real page names.</td>
  </tr>
  <tr>
    <td>Two separate <code>@media (max-width: 1300px)</code> blocks</td>
    <td>Merge them into one.</td>
  </tr>
  <tr>
    <td><code>justify-content: center</code> is written twice in <code>.first</code></td>
    <td>Keep one.</td>
  </tr>
  <tr>
    <td><code>.second</code> and <code>.third</code> classes have no CSS</td>
    <td>Remove them, or use them for section-specific styling.</td>
  </tr>
  <tr>
    <td><code>nav img { color: red; }</code> does nothing on an image</td>
    <td>Remove it.</td>
  </tr>
  <tr>
    <td>The logo has <code>width="53"</code> in HTML but <code>width: 130px</code> in CSS</td>
    <td>CSS wins. Keep only one value.</td>
  </tr>
  <tr>
    <td>The phone number is copied from the real site</td>
    <td>Use a placeholder such as <code>000-000-0000</code>.</td>
  </tr>
</table>

</details>

<details>
<summary><b>5. 🌐 Hosted assets can break, and a local video goes unused</b></summary>

<br>

The TV image, phone image, kids image, and both videos load from Netflix's servers (`assets.nflxext.com`, `nflxso.net`). Those links can change or block hotlinking at any time, and the page won't work offline.

You already have `assets/videos/video1.m4v` locally, but it isn't used.

**Fix:** download the files you're allowed to use into `assets/` and reference them locally:

```html
<video src="assets/videos/video1.m4v" autoplay loop muted playsinline></video>
```

`playsinline` lets the video autoplay inline on iPhones instead of going fullscreen.

</details>

<details>
<summary><b>6. 📐 Fixed hero height</b></summary>

<br>

`.main` and `.box` are both `height: 644px`. On a small phone, the stacked headline, text, and form may need more room and overflow the hero.

**Fix:** use `min-height: 644px` on `.main`, and make the overlay fill its parent with `inset: 0` instead of a repeated height:

```css
.main { min-height: 644px; }

.main .box {
  position: absolute;
  inset: 0;                 /* top, right, bottom, left = 0 */
  background-color: black;
  opacity: 0.69;
}
```

</details>

<details>
<summary><b>7. ♿ Accessibility and performance</b></summary>

<br>

<table>
  <tr>
    <th>Issue</th>
    <th>Fix</th>
  </tr>
  <tr>
    <td>Images that carry meaning have <code>alt=""</code></td>
    <td>Add short descriptions such as <code>alt="TV showing a movie"</code>. Keep an empty <code>alt</code> only for decoration.</td>
  </tr>
  <tr>
    <td>The email field is <code>type="text"</code> and has only a placeholder</td>
    <td>Use <code>type="email"</code> and add <code>aria-label="Email address"</code>.</td>
  </tr>
  <tr>
    <td>"Get Started" and "Sign In" do nothing</td>
    <td>Wrap the form in a <code>&lt;form&gt;</code> and link Sign In to a page.</td>
  </tr>
  <tr>
    <td>Fonts load through <code>@import</code> inside the CSS</td>
    <td>Use <code>&lt;link&gt;</code> tags in the HTML head, with <code>rel="preconnect"</code>, so fonts load sooner.</td>
  </tr>
  <tr>
    <td>The favicon isn't linked</td>
    <td>Add <code>&lt;link rel="icon" href="favicon.ico"&gt;</code>.</td>
  </tr>
  <tr>
    <td>The hero heading is a <code>&lt;span&gt;</code></td>
    <td>Make the headline an <code>&lt;h1&gt;</code> for proper document structure.</td>
  </tr>
  <tr>
    <td>Autoplaying video can bother some users</td>
    <td>Respect <code>prefers-reduced-motion</code> by pausing or hiding the videos.</td>
  </tr>
</table>

</details>

---

## 🚀 How to Run

No installation or build step needed.

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/<your-repo-name>.git

# 2. Move into the project
cd <your-repo-name>

# 3. Open the page in your browser
open index.html      # macOS
start index.html     # Windows
xdg-open index.html  # Linux
```

💡 **Tips:**
- You need an internet connection, because the fonts and several images and videos are hosted online.
- Use the VS Code **Live Server** extension to reload automatically when you save.
- In DevTools (`F12`), open the device toolbar and drag the width across `1300px` to watch the layout change.

---

## 🎓 What I Learned

<table>
  <tr>
    <td>✅</td>
    <td>A non-positioned element paints <b>below</b> a positioned one, which is why the nav needed <code>z-index</code> to appear above the overlay.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>A transparent image on top of a video makes the video look like it's inside the frame.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td><code>max()</code> and <code>calc()</code> let CSS do small calculations, such as a minimum background size or "full height minus the navbar".</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>HTML source order can swap text and image sides without extra CSS.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Flexbox and Grid each have a job: Flexbox for rows and columns of content, Grid for the footer's equal columns.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td><code>* { font-family }</code> sets the font on every element and defeats inheritance. Set fonts on <code>body</code> instead.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Fixed pixel offsets (like the video's <code>top: 51px</code>) don't scale. Tie them to a variable or a percentage.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Hotlinked images and videos are fragile. Keep local copies of assets you're allowed to use.</td>
  </tr>
</table>

---

## 🗺️ Roadmap

- [x] Hero with background photo, overlay, and sign-up form
- [x] Four alternating feature sections
- [x] Video playing inside a TV frame
- [x] FAQ section and footer
- [x] Responsive layout at 1300px
- [ ] Fix the [known issues](#-known-issues--fixes) above
- [ ] Turn the FAQ boxes into a working accordion with `<details>`
- [ ] Move all assets to local files
- [ ] Move colors into CSS variables
- [ ] Add more breakpoints (tablet and phone)
- [ ] Wrap the email field in a form with validation
- [ ] Build a Sign In page
- [ ] Deploy to GitHub Pages

---

<div align="center">

### ⭐ If you found this helpful, consider giving the repo a star!

Made with ❤️ while learning CSS

</div>
