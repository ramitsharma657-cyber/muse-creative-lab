Concept:
A digital moodboard where you can add ideas, colors, typography, images, and design notes.

✨ Main features
🖼️ Moodboard — arrange inspiration cards
🎨 Color Lab — create and save color palettes
🔤 Typography — experiment with font combinations
💡 Idea Vault — save design ideas
📝 Design Notes — record concepts and observations
🔍 Search & Filter — find saved ideas
🌙 Dark/Light aesthetic UI
💾 Local storage — data stays saved in the browser
Visual direction

Think:

MUSE
Creative Inspiration Lab

 ┌──────────────────────────────────────────┐
 │  ✦ Your creative space                  │
 │                                          │
 │  MOODBOARD                               │
 │                                          │
 │  ┌────────┐  ┌─────────────┐             │
 │  │ IMAGE  │  │   PALETTE   │             │
 │  │        │  │ ● ● ● ● ●  │             │
 │  └────────┘  └─────────────┘             │
 │                                          │
 │  ┌────────────────┐ ┌───────────────┐   │
 │  │ DESIGN NOTE    │ │   TYPOGRAPHY  │   │
 │  │ "Less but..."  │ │   Aa  Aa      │   │
 │  └────────────────┘ └───────────────┘   │
 └──────────────────────────────────────────┘
🧑‍💻 Tech

We'll build it with:

HTML → CSS → JavaScript → LocalStorage

Later, we can upgrade it to React and add more advanced features



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>MUSE — Creative Inspiration Lab</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:ital,wght@0,500;1,500&display=swap" rel="stylesheet">

    <link rel="stylesheet" href="style.css">
</head>

<body>

    <header class="navbar">
        <div class="logo">MUSE<span>.</span></div>

        <nav>
            <a href="#moodboard">Moodboard</a>
            <a href="#palette">Palette</a>
            <a href="#ideas">Ideas</a>
        </nav>

        <button id="themeBtn" class="theme-btn">◐</button>
    </header>


    <main>

        <!-- HERO -->
        <section class="hero">
            <div>
                <p class="eyebrow">CREATIVE INSPIRATION LAB</p>

                <h1>
                    Collect ideas.<br>
                    <em>Make something.</em>
                </h1>

                <p class="hero-text">
                    A quiet digital space for designers to collect,
                    explore and develop creative thoughts.
                </p>

                <button class="primary-btn" onclick="scrollToBoard()">
                    Enter the studio →
                </button>
            </div>

            <div class="hero-shape">
                <div class="shape-circle"></div>
                <div class="shape-square"></div>
                <div class="shape-line"></div>
            </div>
        </section>


        <!-- MOODBOARD -->
        <section id="moodboard" class="section">

            <div class="section-heading">
                <div>
                    <p class="eyebrow">01 / MOODBOARD</p>
                    <h2>Visual thoughts</h2>
                </div>

                <button class="outline-btn" onclick="addCard()">
                    + Add idea
                </button>
            </div>

            <div id="ideaGrid" class="idea-grid">

                <article class="idea-card card-large">
                    <div class="card-image gradient-one"></div>
                    <div class="card-content">
                        <span>REFERENCE / 01</span>
                        <h3>Organic forms</h3>
                        <p>Natural shapes, imperfect curves and soft visual rhythm.</p>
                    </div>
                </article>

                <article class="idea-card">
                    <div class="card-image gradient-two"></div>
                    <div class="card-content">
                        <span>REFERENCE / 02</span>
                        <h3>Quiet spaces</h3>
                        <p>Minimal environments with strong negative space.</p>
                    </div>
                </article>

                <article class="idea-card">
                    <div class="card-image gradient-three"></div>
                    <div class="card-content">
                        <span>REFERENCE / 03</span>
                        <h3>Material study</h3>
                        <p>Exploring texture, shadow and tactile surfaces.</p>
                    </div>
                </article>

            </div>
        </section>


        <!-- COLOR LAB -->
        <section id="palette" class="section palette-section">

            <div class="section-heading">
                <div>
                    <p class="eyebrow">02 / COLOR LAB</p>
                    <h2>Build a palette</h2>
                </div>

                <button class="outline-btn" onclick="randomPalette()">
                    Generate palette
                </button>
            </div>

            <div class="palette-card">

                <div class="color color-one">
                    <span>#E8DCC8</span>
                </div>

                <div class="color color-two">
                    <span>#B7C4B2</span>
                </div>

                <div class="color color-three">
                    <span>#7C8B75</span>
                </div>

                <div class="color color-four">
                    <span>#39443B</span>
                </div>

                <div class="color color-five">
                    <span>#171A17</span>
                </div>

            </div>

            <p class="hint">Click "Generate palette" to explore new combinations.</p>

        </section>


        <!-- IDEA VAULT -->
        <section id="ideas" class="section">

            <div class="section-heading">
                <div>
                    <p class="eyebrow">03 / IDEA VAULT</p>
                    <h2>Keep the thought</h2>
                </div>
            </div>

            <div class="idea-form">

                <input
                    id="ideaInput"
                    type="text"
                    placeholder="Write a design idea..."
                >

                <button class="primary-btn" onclick="saveIdea()">
                    Save idea
                </button>

            </div>

            <div id="savedIdeas" class="saved-ideas"></div>

        </section>

    </main>


    <footer>
        <div class="logo">MUSE<span>.</span></div>
        <p>Designed & built as a creative coding experiment.</p>
    </footer>


    <script src="script.js"></script>

</body>
</html>


:root {
    --bg: #f4f1eb;
    --surface: #ebe7df;
    --text: #1d211d;
    --muted: #77766f;
    --border: #d6d1c7;
    --accent: #39443b;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: var(--bg);
    color: var(--text);
    font-family: "DM Sans", sans-serif;
    transition: 0.3s ease;
}


/* NAVBAR */

.navbar {
    height: 80px;
    padding: 0 6%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid var(--border);
}

.logo {
    font-size: 22px;
    font-weight: 700;
    letter-spacing: -1px;
}

.logo span {
    color: #87917e;
}

nav {
    display: flex;
    gap: 35px;
}

nav a {
    color: var(--muted);
    text-decoration: none;
    font-size: 14px;
}

nav a:hover {
    color: var(--text);
}

.theme-btn {
    border: 1px solid var(--border);
    background: transparent;
    width: 38px;
    height: 38px;
    border-radius: 50%;
    cursor: pointer;
    color: var(--text);
}


/* HERO */

.hero {
    min-height: 680px;
    padding: 100px 10%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    gap: 80px;
}

.eyebrow {
    font-size: 11px;
    letter-spacing: 2px;
    color: var(--muted);
    margin-bottom: 20px;
}

h1 {
    font-family: "Playfair Display", serif;
    font-size: clamp(55px, 7vw, 100px);
    font-weight: 500;
    line-height: 0.95;
    letter-spacing: -4px;
}

h1 em {
    color: #6e796b;
}

.hero-text {
    max-width: 430px;
    color: var(--muted);
    line-height: 1.7;
    margin: 35px 0;
}

.primary-btn,
.outline-btn {
    padding: 13px 22px;
    border-radius: 100px;
    cursor: pointer;
    font-family: inherit;
    transition: 0.2s ease;
}

.primary-btn {
    border: none;
    background: var(--accent);
    color: white;
}

.primary-btn:hover {
    transform: translateY(-2px);
}

.outline-btn {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--text);
}

.outline-btn:hover {
    background: var(--surface);
}


/* ABSTRACT HERO ART */

.hero-shape {
    height: 420px;
    position: relative;
}

.shape-circle {
    width: 280px;
    height: 280px;
    border-radius: 50%;
    background: #c8d0c2;
    position: absolute;
    top: 40px;
    left: 20%;
}

.shape-square {
    width: 180px;
    height: 180px;
    background: #b7a997;
    position: absolute;
    right: 8%;
    bottom: 40px;
    transform: rotate(12deg);
}

.shape-line {
    width: 280px;
    height: 4px;
    background: var(--text);
    position: absolute;
    left: 5%;
    bottom: 100px;
    transform: rotate(-25deg);
}


/* SECTIONS */

.section {
    padding: 100px 10%;
    border-top: 1px solid var(--border);
}

.section-heading {
    display: flex;
    justify-content: space-between;
    align-items: end;
    margin-bottom: 50px;
}

h2 {
    font-family: "Playfair Display", serif;
    font-size: 55px;
    font-weight: 500;
}


/* CARDS */

.idea-grid {
    display: grid;
    grid-template-columns: 1.3fr 1fr 1fr;
    gap: 20px;
}

.idea-card {
    background: var(--surface);
    border-radius: 4px;
    overflow: hidden;
}

.card-image {
    height: 270px;
}

.card-large .card-image {
    height: 360px;
}

.gradient-one {
    background:
        radial-gradient(circle at 30% 30%, #d9cdbb 0 18%, transparent 19%),
        linear-gradient(135deg, #a7b29f, #ded5c7);
}

.gradient-two {
    background:
        linear-gradient(45deg, #c5b8a5 25%, transparent 25%),
        linear-gradient(-45deg, #87927f 25%, #d9d2c5 25%);
}

.gradient-three {
    background:
        radial-gradient(circle, #b6c0ae 0 30%, transparent 31%),
        #ded7ca;
}

.card-content {
    padding: 25px;
}

.card-content span {
    font-size: 10px;
    letter-spacing: 1.5px;
    color: var(--muted);
}

.card-content h3 {
    margin: 12px 0 8px;
    font-size: 20px;
}

.card-content p {
    color: var(--muted);
    font-size: 13px;
    line-height: 1.6;
}


/* PALETTE */

.palette-section {
    background: var(--surface);
}

.palette-card {
    height: 300px;
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    overflow: hidden;
    border-radius: 5px;
}

.color {
    display: flex;
    align-items: end;
    padding: 25px;
    transition: 0.3s;
}

.color:hover {
    transform: scale(1.03);
}

.color span {
    font-size: 12px;
    background: rgba(255,255,255,0.5);
    padding: 5px 8px;
    border-radius: 20px;
}

.color-one {
    background: #e8dcc8;
}

.color-two {
    background: #b7c4b2;
}

.color-three {
    background: #7c8b75;
}

.color-four {
    background: #39443b;
}

.color-five {
    background: #171a17;
    color: white;
}

.hint {
    margin-top: 15px;
    color: var(--muted);
    font-size: 12px;
}


/* IDEA VAULT */

.idea-form {
    display: flex;
    gap: 12px;
    max-width: 700px;
}

.idea-form input {
    flex: 1;
    padding: 16px 20px;
    border: 1px solid var(--border);
    background: transparent;
    border-radius: 100px;
    outline: none;
    color: var(--text);
    font-family: inherit;
}

.saved-ideas {
    margin-top: 30px;
    display: grid;
    gap: 10px;
}

.saved-item {
    padding: 18px 20px;
    background: var(--surface);
    border-left: 3px solid #87917e;
}


/* FOOTER */

footer {
    padding: 60px 10%;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    color: var(--muted);
}


/* DARK MODE */

body.dark {
    --bg: #151815;
    --surface: #202420;
    --text: #eeeae2;
    --muted: #999c95;
    --border: #353935;
    --accent: #d9ded5;
}

body.dark .primary-btn {
    color: #151815;
}

body.dark .shape-circle {
    background: #687365;
}

body.dark .shape-square {
    background: #75695d;
}


/* RESPONSIVE */

@media (max-width: 800px) {

    nav {
        display: none;
    }

    .hero {
        grid-template-columns: 1fr;
        padding: 70px 7%;
    }

    .hero-shape {
        height: 300px;
    }

    .section {
        padding: 70px 7%;
    }

    .idea-grid {
        grid-template-columns: 1fr;
    }

    .palette-card {
        height: 220px;
    }

    h2 {
        font-size: 42px;
    }

    .section-heading {
        align-items: start;
        gap: 20px;
        flex-direction: column;
    }

    .idea-form {
        flex-direction: column;
    }

    footer {
        flex-direction: column;
        gap: 15px;
    }
}

// -----------------------------
// DARK / LIGHT MODE
// -----------------------------

const themeBtn = document.getElementById("themeBtn");

themeBtn.addEventListener("click", () => {
    document.body.classList.toggle("dark");

    if (document.body.classList.contains("dark")) {
        themeBtn.textContent = "☀";
    } else {
        themeBtn.textContent = "◐";
    }
});


// -----------------------------
// SCROLL TO MOODBOARD
// -----------------------------

function scrollToBoard() {
    document.getElementById("moodboard").scrollIntoView({
        behavior: "smooth"
    });
}


// -----------------------------
// ADD IDEA CARD
// -----------------------------

function addCard() {

    const title = prompt("Give your idea a name:");

    if (!title) return;

    const description = prompt("Describe your idea:");

    if (!description) return;

    const grid = document.getElementById("ideaGrid");

    const card = document.createElement("article");

    card.className = "idea-card";

    card.innerHTML = `
        <div class="card-image gradient-three"></div>

        <div class="card-content">
            <span>NEW IDEA</span>
            <h3>${escapeHTML(title)}</h3>
            <p>${escapeHTML(description)}</p>
        </div>
    `;

    grid.appendChild(card);
}


// -----------------------------
// SAVE IDEA
// -----------------------------

function saveIdea() {

    const input = document.getElementById("ideaInput");

    const text = input.value.trim();

    if (!text) {
        alert("Write an idea first.");
        return;
    }

    const ideas = JSON.parse(
        localStorage.getItem("museIdeas") || "[]"
    );

    ideas.push(text);

    localStorage.setItem(
        "museIdeas",
        JSON.stringify(ideas)
    );

    input.value = "";

    displayIdeas();
}


// -----------------------------
// DISPLAY SAVED IDEAS
// -----------------------------

function displayIdeas() {

    const container = document.getElementById("savedIdeas");

    const ideas = JSON.parse(
        localStorage.getItem("museIdeas") || "[]"
    );

    container.innerHTML = "";

    ideas.forEach((idea, index) => {

        const item = document.createElement("div");

        item.className = "saved-item";

        item.innerHTML = `
            <strong>Idea ${index + 1}</strong>
            <p>${escapeHTML(idea)}</p>
        `;

        container.appendChild(item);
    });
}


// -----------------------------
// RANDOM COLOR PALETTE
// -----------------------------

function randomPalette() {

    const colors = [
        "#D8C7B5",
        "#A9B5A1",
        "#6D796B",
        "#343B35",
        "#171A17",

        "#D6C8C0",
        "#B8A9A0",
        "#82756D",
        "#4C4642",
        "#242321",

        "#D7D0BA",
        "#AAB39A",
        "#77806A",
        "#48513F",
        "#20251D"
    ];

    const colorElements =
        document.querySelectorAll(".color");

    colorElements.forEach((element) => {

        const randomColor =
            colors[Math.floor(Math.random() * colors.length)];

        element.style.background = randomColor;

        const text = element.querySelector("span");

        text.textContent =
            randomColor.toUpperCase();
    });
}


// -----------------------------
// BASIC HTML ESCAPING
// -----------------------------

function escapeHTML(text) {

    const div = document.createElement("div");

    div.textContent = text;

    return div.innerHTML;
}


// Load saved ideas when page opens
displayIdeas();
