
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Happy Teachers' Day | Sir Randy Bello</title>

    <style>
        /* =========================================
           MARVEL TEACHER'S DAY CARD
           HTML + CSS + JAVASCRIPT IN ONE FILE
        ========================================== */

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --red: #e62429;
            --dark-red: #9b111e;
            --gold: #ffd700;
            --black: #080808;
            --dark: #111111;
            --white: #ffffff;
            --gray: #cccccc;
            --card: rgba(20, 20, 20, 0.92);
            --shadow: rgba(230, 36, 41, 0.45);
        }

        body.light {
            --black: #f5f5f5;
            --dark: #ffffff;
            --white: #151515;
            --gray: #444444;
            --card: rgba(255, 255, 255, 0.95);
            --shadow: rgba(230, 36, 41, 0.25);
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            min-height: 100vh;
            overflow-x: hidden;
            font-family: Arial, Helvetica, sans-serif;
            color: var(--white);
            background:
                radial-gradient(circle at 20% 20%, rgba(230,36,41,.18), transparent 30%),
                radial-gradient(circle at 80% 80%, rgba(255,215,0,.08), transparent 30%),
                var(--black);
            transition:
                background 0.7s ease,
                color 0.7s ease;
        }

        /* =========================================
           BACKGROUND
        ========================================== */

        .background {
            position: fixed;
            inset: 0;
            overflow: hidden;
            z-index: -5;
        }

        .background::before {
            content: "";
            position: absolute;
            inset: 0;
            background:
                linear-gradient(
                    135deg,
                    transparent 45%,
                    rgba(230,36,41,.05) 45%,
                    rgba(230,36,41,.05) 55%,
                    transparent 55%
                );
            background-size: 90px 90px;
            animation: moveBackground 15s linear infinite;
        }

        @keyframes moveBackground {
            from {
                background-position: 0 0;
            }
            to {
                background-position: 180px 180px;
            }
        }

        .particle {
            position: absolute;
            width: 5px;
            height: 5px;
            border-radius: 50%;
            background: var(--gold);
            box-shadow: 0 0 12px var(--gold);
            opacity: .6;
            animation: floatParticle linear infinite;
        }

        @keyframes floatParticle {
            0% {
                transform: translateY(100vh) scale(.5);
                opacity: 0;
            }

            20% {
                opacity: .8;
            }

            80% {
                opacity: .8;
            }

            100% {
                transform: translateY(-10vh) scale(1.3);
                opacity: 0;
            }
        }

        /* =========================================
           TOP BAR
        ========================================== */

        .topbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 70px;
            padding: 0 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;

            background: rgba(5,5,5,.72);
            backdrop-filter: blur(15px);
            border-bottom: 1px solid rgba(255,255,255,.1);
        }

        body.light .topbar {
            background: rgba(255,255,255,.78);
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 12px;
            font-weight: bold;
            letter-spacing: 1px;
        }

        .brand-icon {
            width: 40px;
            height: 40px;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 50%;
            background: var(--red);
            box-shadow:
                0 0 15px rgba(230,36,41,.7),
                inset 0 0 10px rgba(255,255,255,.2);
            animation: iconPulse 2s infinite;
        }

        @keyframes iconPulse {
            0%,100% {
                transform: scale(1);
                box-shadow: 0 0 15px rgba(230,36,41,.6);
            }

            50% {
                transform: scale(1.08);
                box-shadow: 0 0 30px rgba(230,36,41,.9);
            }
        }

        .theme-btn {
            border: 1px solid var(--red);
            background: transparent;
            color: var(--white);
            padding: 10px 18px;
            border-radius: 30px;
            cursor: pointer;
            font-weight: bold;
            transition: .3s;
        }

        .theme-btn:hover {
            background: var(--red);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 0 20px var(--shadow);
        }

        /* =========================================
           HERO
        ========================================== */

        .hero {
            min-height: 100vh;
            padding: 120px 20px 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        .hero-content {
            max-width: 1000px;
            animation: heroEnter 1.3s ease forwards;
        }

        @keyframes heroEnter {
            from {
                opacity: 0;
                transform: translateY(50px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .marvel-logo {
            display: inline-block;
            padding: 10px 22px;
            margin-bottom: 25px;
            background: var(--red);
            color: white;
            font-size: 1.5rem;
            font-weight: 900;
            letter-spacing: 4px;
            transform: skew(-8deg);
            box-shadow: 0 0 30px rgba(230,36,41,.55);
            animation: logoGlow 2.5s infinite alternate;
        }

        @keyframes logoGlow {
            from {
                box-shadow: 0 0 15px rgba(230,36,41,.4);
            }

            to {
                box-shadow:
                    0 0 35px rgba(230,36,41,.8),
                    0 0 70px rgba(230,36,41,.3);
            }
        }

        .hero h1 {
            font-size: clamp(3rem, 8vw, 7rem);
            line-height: .95;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: -3px;

            background: linear-gradient(
                90deg,
                var(--red),
                var(--gold),
                var(--red)
            );

            background-size: 200% auto;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;

            animation: shineText 4s linear infinite;
        }

        @keyframes shineText {
            to {
                background-position: 200% center;
            }
        }

        .hero h2 {
            margin-top: 25px;
            font-size: clamp(1.4rem, 4vw, 2.5rem);
            color: var(--gray);
        }

        .hero h2 span {
            color: var(--red);
            font-weight: 900;
        }

        .hero p {
            max-width: 700px;
            margin: 25px auto;
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--gray);
        }

        .start-btn {
            margin-top: 20px;
            padding: 16px 35px;
            border: none;
            border-radius: 50px;
            background: linear-gradient(135deg, var(--red), var(--dark-red));
            color: white;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 10px 30px rgba(230,36,41,.35);
            transition: .35s;
        }

        .start-btn:hover {
            transform: translateY(-5px) scale(1.03);
            box-shadow:
                0 15px 40px rgba(230,36,41,.55),
                0 0 30px rgba(230,36,41,.3);
        }

        /* =========================================
           LETTER SECTION
        ========================================== */

        .letter-section {
            min-height: 100vh;
            padding: 100px 20px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .letter-wrapper {
            width: min(850px, 95vw);
            perspective: 1500px;
        }

        /* Envelope */

        .envelope {
            position: relative;
            height: 500px;
            background: #74151a;
            border-radius: 15px;
            box-shadow:
                0 30px 70px rgba(0,0,0,.6),
                0 0 50px rgba(230,36,41,.18);

            cursor: pointer;
            overflow: hidden;
            transition: .6s;
        }

        .envelope:hover {
            transform: translateY(-8px);
        }

        .envelope-back {
            position: absolute;
            inset: 0;
            background:
                linear-gradient(135deg, #b51b21, #5a0b10);
        }

        .envelope-flap {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 55%;
            z-index: 4;

            background: linear-gradient(
                145deg,
                #d8272d,
                #801116
            );

            clip-path: polygon(0 0, 100% 0, 50% 100%);
            transform-origin: top;
            transition: transform 1.2s cubic-bezier(.77,0,.18,1);
            box-shadow: 0 10px 20px rgba(0,0,0,.2);
        }

        .envelope.open .envelope-flap {
            transform: rotateX(180deg);
            z-index: 1;
        }

        .envelope-front {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 55%;
            z-index: 3;

            background:
                linear-gradient(
                    135deg,
                    #9f151b,
                    #681016
                );

            clip-path: polygon(
                0 0,
                50% 55%,
                100% 0,
                100% 100%,
                0 100%
            );
        }

        .shield {
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            width: 130px;
            height: 130px;
            border-radius: 50%;
            background:
                radial-gradient(
                    circle,
                    var(--gold) 0 20%,
                    white 21% 35%,
                    var(--red) 36% 60%,
                    white 61% 72%,
                    var(--red) 73%
                );

            z-index: 5;
            box-shadow:
                0 0 30px rgba(255,215,0,.45),
                inset 0 0 15px rgba(0,0,0,.3);

            transition: 1s;
        }

        .envelope.open .shield {
            opacity: 0;
            transform:
                translate(-50%, -50%)
                scale(2);
        }

        .open-text {
            position: absolute;
            bottom: 40px;
            width: 100%;
            text-align: center;
            z-index: 6;
            color: white;
            font-weight: bold;
            letter-spacing: 2px;
            animation: bounce 1.5s infinite;
        }

        @keyframes bounce {
            0%,100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-7px);
            }
        }

        /* =========================================
           LETTER PAPER
        ========================================== */

        .letter {
            position: absolute;
            width: 88%;
            height: 88%;
            left: 6%;
            top: 6%;
            padding: 45px;

            overflow-y: auto;

            background:
                linear-gradient(
                    135deg,
                    #fffdf4,
                    #f3ead4
                );

            color: #171717;
            border-radius: 8px;

            z-index: 2;

            transform:
                translateY(120px)
                scale(.85);

            opacity: 0;

            transition:
                transform 1.2s cubic-bezier(.77,0,.18,1),
                opacity .7s ease;

            box-shadow:
                0 20px 50px rgba(0,0,0,.45);
        }

        .envelope.open .letter {
            transform:
                translateY(-10px)
                scale(1);

            opacity: 1;
            transition-delay: .45s;
            z-index: 5;
        }

        .letter::-webkit-scrollbar {
            width: 7px;
        }

        .letter::-webkit-scrollbar-thumb {
            background: var(--red);
            border-radius: 10px;
        }

        .letter-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .letter-header .star {
            font-size: 3rem;
            color: var(--red);
            animation: starSpin 5s linear infinite;
        }

        @keyframes starSpin {
            from {
                transform: rotate(0);
            }

            to {
                transform: rotate(360deg);
            }
        }

        .letter h2 {
            font-size: clamp(1.8rem, 5vw, 3rem);
            color: var(--red);
            margin: 10px 0;
        }

        .letter .subtitle {
            color: #555;
            font-style: italic;
        }

        .letter-body {
            font-family: Georgia, serif;
            font-size: 1.12rem;
            line-height: 1.9;
        }

        .letter-body p {
            margin-bottom: 18px;
        }

        .highlight {
            color: var(--red);
            font-weight: bold;
        }

        .quote {
            margin: 25px 0;
            padding: 20px;
            border-left: 5px solid var(--red);
            background: rgba(230,36,41,.07);
            font-size: 1.15rem;
            font-style: italic;
        }

        .signature {
            margin-top: 35px;
            text-align: right;
            font-family: "Brush Script MT", cursive;
            font-size: 2rem;
            color: var(--red);
        }

        /* =========================================
           POWER SECTION
        ========================================== */

        .power-section {
            padding: 100px 20px;
            text-align: center;
        }

        .section-title {
            font-size: clamp(2rem, 6vw, 4rem);
            text-transform: uppercase;
            margin-bottom: 50px;
            color: var(--white);
        }

        .section-title span {
            color: var(--red);
        }

        .powers {
            max-width: 1000px;
            margin: auto;
            display: grid;
            grid-template-columns:
                repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
        }

        .power-card {
            padding: 35px 20px;
            background: var(--card);
            border: 1px solid rgba(230,36,41,.3);
            border-radius: 18px;
            transition: .4s;
            box-shadow: 0 15px 35px rgba(0,0,0,.2);
        }

        .power-card:hover {
            transform: translateY(-10px);
            border-color: var(--red);
            box-shadow:
                0 20px 50px rgba(230,36,41,.25);
        }

        .power-icon {
            font-size: 3rem;
            margin-bottom: 15px;
        }

        .power-card h3 {
            color: var(--red);
            margin-bottom: 10px;
        }

        .power-card p {
            color: var(--gray);
            line-height: 1.6;
        }

        /* =========================================
           FOOTER
        ========================================== */

        footer {
            padding: 50px 20px;
            text-align: center;
            border-top: 1px solid rgba(255,255,255,.1);
        }

        footer h3 {
            color: var(--red);
            margin-bottom: 10px;
        }

        footer p {
            color: var(--gray);
        }

        .heart {
            color: var(--red);
            animation: heartbeat 1.2s infinite;
            display: inline-block;
        }

        @keyframes heartbeat {
            0%,100% {
                transform: scale(1);
            }

            50% {
                transform: scale(1.3);
            }
        }

        /* =========================================
           MUSIC BUTTON
        ========================================== */

        .music-btn {
            position: fixed;
            right: 25px;
            bottom: 25px;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            border: 2px solid var(--red);
            background: var(--card);
            color: var(--white);
            cursor: pointer;
            z-index: 1000;
            font-size: 1.3rem;
            transition: .3s;
        }

        .music-btn:hover {
            transform: scale(1.1);
            background: var(--red);
            color: white;
        }

        /* =========================================
           MOBILE
        ========================================== */

        @media (max-width: 700px) {

            .topbar {
                padding: 0 15px;
            }

            .brand span {
                display: none;
            }

            .hero {
                padding-top: 100px;
            }

            .hero h1 {
                letter-spacing: -1px;
            }

            .letter-section {
                padding: 60px 10px;
            }

            .envelope {
                height: 600px;
            }

            .letter {
                width: 94%;
                left: 3%;
                padding: 25px;
            }

            .letter-body {
                font-size: 1rem;
            }

            .shield {
                width: 100px;
                height: 100px;
            }
        }

        /* =========================================
           OPEN ANIMATION EFFECT
        ========================================== */

        .flash {
            position: fixed;
            inset: 0;
            background: white;
            z-index: 5000;
            pointer-events: none;
            opacity: 0;
        }

        .flash.active {
            animation: flashEffect .8s ease;
        }

        @keyframes flashEffect {
            0% {
                opacity: 0;
            }

            25% {
                opacity: .8;
            }

            100% {
                opacity: 0;
            }
        }

    </style>
</head>

<body>

    <!-- BACKGROUND -->
    <div class="background" id="particles"></div>

    <!-- FLASH EFFECT -->
    <div class="flash" id="flash"></div>

    <!-- TOP NAVIGATION -->
    <header class="topbar">

        <div class="brand">
            <div class="brand-icon">★</div>
            <span>MARVEL TEACHERS' DAY</span>
        </div>

        <button class="theme-btn" id="themeBtn">
            🌙 Dark Mode
        </button>

    </header>


    <!-- HERO -->
    <section class="hero">

        <div class="hero-content">

            <div class="marvel-logo">
                MARVEL
            </div>

            <h1>
                Happy<br>
                Teachers' Day
            </h1>

            <h2>
                To Our <span>Web Development Hero</span>
            </h2>

            <p>
                A special tribute to the teacher who turns lines of code
                into ideas, challenges into opportunities, and students
                into future developers.
            </p>

            <button class="start-btn" id="openLetterBtn">
                ✉️ Open Your Letter
            </button>

        </div>

    </section>


    <!-- LETTER -->
    <section class="letter-section" id="letterSection">

        <div class="letter-wrapper">

            <div class="envelope" id="envelope">

                <div class="envelope-back"></div>

                <!-- LETTER PAPER -->
                <article class="letter">

                    <div class="letter-header">

                        <div class="star">★</div>

                        <h2>
                            Dear Sir Randy Bello
                        </h2>

                        <div class="subtitle">
                            Our Web Development Hero
                        </div>

                    </div>

                    <div class="letter-body">

                        <p>
                            <span class="highlight">Happy Teachers' Day, Sir Randy!</span>
                        </p>

                        <p>
                            Today, I want to take a moment to say
                            <strong>thank you</strong> for being more than
                            just a Web Development instructor.
                        </p>

                        <p>
                            You have taught us that programming is not
                            simply about writing code. It is about
                            <span class="highlight">
                                creativity, patience, problem-solving,
                                determination, and never giving up
                            </span>
                            when something does not work on the first try.
                        </p>

                        <div class="quote">
                            "Every great developer was once a beginner
                            who refused to stop learning."
                        </div>

                        <p>
                            Your lessons have helped us understand how
                            websites are built, but more importantly,
                            you have encouraged us to believe that
                            <strong>we can create something meaningful
                            with our own ideas and skills.</strong>
                        </p>

                        <p>
                            There are times when our code gives us errors,
                            our programs do not work, or our designs do
                            not look the way we imagined. But through
                            your guidance, we learn to debug,
                            try again, and keep moving forward.
                        </p>

                        <p>
                            Just like a Marvel hero facing a difficult
                            mission, you remind us that challenges are
                            part of becoming stronger.
                        </p>

                        <p>
                            Thank you for sharing your knowledge,
                            spending your time teaching us, and inspiring
                            us to become better students and future
                            professionals.
                        </p>

                        <p>
                            May you continue to inspire many more students
                            and create future developers who will carry
                            the lessons you have taught us wherever they go.
                        </p>

                        <p>
                            You are truly one of our
                            <span class="highlight">
                                real-life heroes.
                            </span>
                        </p>

                        <div class="signature">

                            With gratitude,<br>

                            Your Student ❤️

                        </div>

                    </div>

                </article>


                <!-- FLAP -->
                <div class="envelope-flap"></div>

                <!-- SHIELD -->
                <div class="shield"></div>

                <!-- FRONT -->
                <div class="envelope-front"></div>

                <div class="open-text">
                    CLICK TO OPEN THE LETTER
                </div>

            </div>

        </div>

    </section>


    <!-- HERO QUALITIES -->
    <section class="power-section">

        <h2 class="section-title">
            What Makes You A <span>Hero?</span>
        </h2>

        <div class="powers">

            <div class="power-card">

                <div class="power-icon">💡</div>

                <h3>Inspiration</h3>

                <p>
                    You inspire students to turn their ideas
                    into real digital creations.
                </p>

            </div>


            <div class="power-card">

                <div class="power-icon">💻</div>

                <h3>Knowledge</h3>

                <p>
                    You share valuable programming and web
                    development knowledge with us.
                </p>

            </div>


            <div class="power-card">

                <div class="power-icon">🛡️</div>

                <h3>Patience</h3>

                <p>
                    You guide us through difficult problems
                    and help us understand our mistakes.
                </p>

            </div>


            <div class="power-card">

                <div class="power-icon">🚀</div>

                <h3>Motivation</h3>

                <p>
                    You encourage us to keep learning,
                    improving, and reaching our goals.
                </p>

            </div>

        </div>

    </section>


    <!-- FOOTER -->
    <footer>

        <h3>
            HAPPY TEACHERS' DAY, SIR RANDY BELLO!
        </h3>

        <p>
            Thank you for helping us become the developers
            we dream of becoming.
        </p>

        <br>

        <p>
            Made with <span class="heart">♥</span>
            and lots of code.
        </p>

    </footer>


    <!-- MUSIC BUTTON -->
    <button class="music-btn" id="musicBtn" title="Play Music">
        🔊
    </button>


    <script>

        /* =========================================
           LETTER OPENING
        ========================================== */

        const envelope =
            document.getElementById("envelope");

        const openLetterBtn =
            document.getElementById("openLetterBtn");

        const letterSection =
            document.getElementById("letterSection");

        const flash =
            document.getElementById("flash");


        function openLetter() {

            envelope.classList.add("open");

            flash.classList.remove("active");

            void flash.offsetWidth;

            flash.classList.add("active");

            setTimeout(() => {

                letterSection.scrollIntoView({
                    behavior: "smooth"
                });

            }, 500);

        }


        envelope.addEventListener(
            "click",
            openLetter
        );

        openLetterBtn.addEventListener(
            "click",
            openLetter
        );


        /* =========================================
           DARK / LIGHT MODE
        ========================================== */

        const themeBtn =
            document.getElementById("themeBtn");


        themeBtn.addEventListener(
            "click",
            () => {

                document.body.classList.toggle("light");

                const isLight =
                    document.body.classList.contains("light");

                if (isLight) {

                    themeBtn.innerHTML =
                        "☀️ Light Mode";

                    localStorage.setItem(
                        "theme",
                        "light"
                    );

                } else {

                    themeBtn.innerHTML =
                        "🌙 Dark Mode";

                    localStorage.setItem(
                        "theme",
                        "dark"
                    );

                }

            }
        );


        /* =========================================
           REMEMBER THEME
        ========================================== */

        const savedTheme =
            localStorage.getItem("theme");


        if (savedTheme === "light") {

            document.body.classList.add("light");

            themeBtn.innerHTML =
                "☀️ Light Mode";

        }


        /* =========================================
           CREATE FLOATING PARTICLES
        ========================================== */

        const particles =
            document.getElementById("particles");


        for (let i = 0; i < 45; i++) {

            const particle =
                document.createElement("div");

            particle.classList.add("particle");

            particle.style.left =
                Math.random() * 100 + "%";

            particle.style.animationDuration =
                (5 + Math.random() * 10) + "s";

            particle.style.animationDelay =
                Math.random() * 10 + "s";

            const size =
                2 + Math.random() * 5;

            particle.style.width =
                size + "px";

            particle.style.height =
                size + "px";

            particles.appendChild(particle);

        }


        /* =========================================
           OPTIONAL MUSIC
           
           Replace MUSIC_URL with your own
           audio file or online audio source.
        ========================================== */

        const musicBtn =
            document.getElementById("musicBtn");

        let musicPlaying = false;

        /*
            To add music, you can replace
            the Audio source below with your
            own audio file.

            Example:

            const music = new Audio("music.mp3");
        */

        const music =
            new Audio();

        music.loop = true;


        musicBtn.addEventListener(
            "click",
            () => {

                if (!music.src) {

                    alert(
                        "Add your own music file by setting the music.src in the JavaScript section."
                    );

                    return;

                }

                if (!musicPlaying) {

                    music.play();

                    musicPlaying = true;

                    musicBtn.innerHTML = "⏸️";

                } else {

                    music.pause();

                    musicPlaying = false;

                    musicBtn.innerHTML = "🔊";

                }

            }
        );


        /* =========================================
           KEYBOARD SHORTCUT
        ========================================== */

        document.addEventListener(
            "keydown",
            (event) => {

                if (event.key === "Enter") {

                    openLetter();

                }

            }
        );


        /* =========================================
           CARD 3D MOUSE EFFECT
        ========================================== */

        envelope.addEventListener(
            "mousemove",
            (event) => {

                if (envelope.classList.contains("open"))
                    return;

                const rect =
                    envelope.getBoundingClientRect();

                const x =
                    event.clientX - rect.left;

                const y =
                    event.clientY - rect.top;

                const rotateY =
                    ((x / rect.width) - .5) * 8;

                const rotateX =
                    ((y / rect.height) - .5) * -8;

                envelope.style.transform =
                    `rotateX(${rotateX}deg)
                     rotateY(${rotateY}deg)
                     translateY(-5px)`;

            }
        );


        envelope.addEventListener(
            "mouseleave",
            () => {

                if (
                    !envelope.classList.contains("open")
                ) {

                    envelope.style.transform =
                        "rotateX(0) rotateY(0)";

                }

            }
        );

    </script>

</body>
</html>
