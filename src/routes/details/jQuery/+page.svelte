<script>
        import { onMount } from 'svelte';
        import Home from '$lib/img/jQuery/home.svg';
        import Arrow from '$lib/img/jQuery/arrow.svg';
        import ElementSelektion from '$lib/img/jQuery/Element-Selektion-im-DOM.jpg';
        import DOM from '$lib/img/jQuery/Dokument-Objekt-Model_Manipulation.jpg';
        import EventSystem from '$lib/img/jQuery/Erweitertes_Event-System.jpg';
        import Animation from '$lib/img/jQuery/Animation-Effekte.jpg';
        import Ajax from '$lib/img/jQuery/ajax.jpg';
        import Logo from '$lib/img/jQuery/logo.png';
        import '$lib/fonts/stylesheet.css';

        let cursorStyle = '';
        let hoverLabelStyle = '';
        let hoverLabelClass = '';
        let activeSlideID = 0;
        let cursor;
        let hoverLabel;

        onMount(() => {
                cursor = document.querySelector('.cursor');
                hoverLabel = document.querySelector('.hover-label');

                document.addEventListener('mousemove', handleMouseMove);
                document.addEventListener('mouseover', handleMouseOver);
                document.addEventListener('mouseout', handleMouseOut);
                document.addEventListener('click', handleClick);

                // Content einblenden durch Klicken
                const slides = document.querySelectorAll('.slide');
                slides[0].classList.add('active-slider');
                slides.forEach((slide) => {
                        slide.addEventListener('click', setActiveSlide);
                });
                console.log(slides);
                // Scroll transition
                const scrollArrows = document.querySelectorAll('.scroll-arrow');
                scrollArrows.forEach((arrow) => {
                        arrow.addEventListener('click', handleScroll);
                });
        });

        function handleMouseMove(event) {
                cursorStyle = `top: ${event.clientY}px; left: ${event.clientX}px;`;
                hoverLabelStyle = `top: ${event.clientY - 15}px; left: ${event.clientX + 40}px;`;
        }

        function handleMouseOver(event) {
                cursorStyle = 'transform: scale(3);';
                if (event.target.classList.contains('slide') && getComputedStyle(event.target).opacity === '0') {
                        hoverLabelClass = 'show';
                } else {
                        hoverLabelClass = '';
                }
        }

        function handleMouseOut() {
                cursorStyle = 'transform: scale(1);';
                hoverLabelClass = '';
        }

        function handleClick() {
                cursorStyle = 'transform: scale(3);';
                setTimeout(function () {
                        cursorStyle = 'transform: scale(1);';
                        hoverLabelClass = '';
                }, 500);
        }

        function setActiveSlide(event) {
                console.log(event.target.closest('.slide').classList[event.target.closest('.slide').classList.length - 1]);
                const slideID = event.target.closest('.slide').classList[event.target.closest('.slide').classList.length - 1];
                if (slideID !== activeSlideID) {
                        activeSlideID = slideID;
                }
        }

        function handleScroll(event) {
                event.preventDefault();

                const target = document.querySelector(event.target.hash);
                const offset = target.offsetTop;

                window.scrollTo({
                        top: offset,
                        behavior: 'smooth',
                });
        }

        onMount(() => {
                const scrollArrow = document.querySelector('.scroll-arrow');
                scrollArrow.addEventListener('click', function (event) {
                        if (this.hash !== '') {
                                event.preventDefault();

                                const hash = this.hash;

                                window.scrollTo({
                                        top: document.querySelector(hash).offsetTop,
                                        behavior: 'smooth',
                                });
                        }
                });
        });
</script>

<div on:mousemove={handleMouseMove} style={cursorStyle} class="cursor" />
<div on:mouseover={handleMouseOver} on:focus={() => {}} />
<div style={hoverLabelStyle} class:show={hoverLabelClass} class="hover-label" />

<body>
        <!-- <a href="#" class="cursor"></a> -->
        <div class="hover-label">Click to <br /> show content</div>
        <header class="site-header">
                <div class="site-header-row">
                        <div class="site-header-column_left">
                                <div class="site-header-home">
                                        <button
                                                ><a href="/">
                                                        <img src={Home} alt="Home" />
                                                </a></button
                                        >
                                </div>
                        </div>
                        <div class="site-header-column_right">
                                <div class="site-header-logo">
                                        <img src={Logo} alt="Logo" />
                                </div>
                        </div>
                </div>
        </header>

        <main>
                <section class="containerOne">
                        <div class="sectionOne">
                                <div class="sectionOne-row">
                                        <div class="sectionOne-kategorie">01 About</div>
                                        <h1><span>jQuery</span> ist eine <br /> JavaScript-Bibliothek für <br /> Web-Interaktionen.</h1>
                                </div>
                        </div>
                        <a href="#containerTwo" class="scroll-arrow">
                                <img src={Arrow} alt="Arrow" />
                        </a>
                </section>
                <section id="containerTwo" class="containerTwo">
                        <div class="sectionTwo-kategorie">02 Quickfacts</div>
                        <div class="sectionTwo-tile01">
                                <h3>jQuery ist eine <br /> JavaScript-Bibliothek</h3>
                                <p>
                                        jQuery ist eine JavaScript-Bibliothek, die das Schreiben von Code erleichtert und beschleunigt. Sie bietet viele Funktionen und Methoden für
                                        die DOM-Manipulation, Ereignisverwaltung, Animationen und Ajax-Requests.
                                </p>
                        </div>
                        <div class="sectionTwo-tile02">
                                <h3>jQuery wurde 2006 veröffentlicht</h3>
                                <p>
                                        jQuery wurde im Jahr 2006 von John Resig veröffentlicht und hat sich seitdem zu einer der am häufigsten verwendeten JavaScript-Bibliotheken
                                        entwickelt.
                                </p>
                        </div>
                        <div class="sectionTwo-tile03">
                                <h3>jQuery bietet eine <br /> Vielzahl an Plug-ins</h3>
                                <p>
                                        jQuery hat eine große Community, die ständig neue Plug-ins und Erweiterungen erstellt, um die Funktionalität von jQuery zu erweitern. Es
                                        gibt eine Vielzahl von Plug-ins für die Erstellung von Benutzeroberflächen, Tabellen, Diagrammen, Diagrammen und vielem mehr.
                                </p>
                        </div>
                        <div class="sectionTwo-tile04">
                                <h3>jQuery ist nicht mehr die einzige Option</h3>
                                <p>
                                        Während jQuery immer noch sehr beliebt ist, gibt es mittlerweile viele andere JavaScript-Bibliotheken und Frameworks, die ähnliche
                                        Funktionen bieten. Einige der beliebtesten Alternativen zu jQuery sind React, Vue.js, Angular und Ember.js.
                                </p>
                        </div>
                </section>
                <section class="containerThree">
                        <div class="sectionThree-kategorie">03 Examples</div>
                        <div class="carousel-slides">
                                <div class="slide active-slider">
                                        <div class="carousel-img">
                                                <img src={ElementSelektion} alt="Element Sektion im DOM" />
                                        </div>
                                        <div class="carousel-content">
                                                <h3>Elementselektion im Document Object Model (DOM)</h3>
                                                <p>
                                                        Mit Hilfe von jQuery können bestimmte HTML-Elemente auf einer Webseite ausgewählt werden und Interaktionen mit ihnen durch
                                                        eine Vielzahl von Selektoren, wie z.B. Klassen, IDs oder Eigenschaften ermöglicht werden. Mit komplexen Selektoren können
                                                        auch Elemente basierend auf ihrer Beziehung zu anderen Elementen ausgewählt werden. Nach der Auswahl eines Elements können
                                                        verschiedene Aktionen ausgeführt werden, z.B. das Ändern des Inhalts, Hinzufügen oder Entfernen von Klassen oder das Binden
                                                        von Ereignissen.
                                                </p>
                                        </div>
                                </div>
                                <div class="slide">
                                        <div class="carousel-img">
                                                <img src={DOM} alt="Dokument-Objekt-Model Manipulation" />
                                        </div>
                                        <div class="carousel-content">
                                                <h3>Dokument-Objekt-Model Manipulation</h3>
                                                <p>
                                                        Die Dokument-Objekt-Model-Manipulation in jQuery ermöglicht es, das DOM einfach und schnell zu manipulieren. Durch die
                                                        Verwendung von CSS-Selektoren und jQuery-Methoden können Elemente schnell und einfach gefunden und bearbeitet werden, z.B.
                                                        durch Ändern ihrer Eigenschaften oder Einfügen von HTML-Inhalten. Die Manipulation ist sehr leistungsfähig und kann für
                                                        dynamische Benutzeroberflächen, Interaktionen oder Layout-Änderungen eingesetzt werden.
                                                </p>
                                        </div>
                                </div>
                                <div class="slide">
                                        <div class="carousel-img">
                                                <img src={EventSystem} alt="Erweitertes Event-System" />
                                        </div>
                                        <div class="carousel-content">
                                                <h3>Erweitertes Event-System</h3>
                                                <p>
                                                        Das erweiterte Event-System von jQuery ermöglicht es, Ereignisse auf einfache und effiziente Weise zu verarbeiten. Mit
                                                        jQuery können Event-Handler auf verschiedene Arten registriert werden, und auch benutzerdefinierte Ereignisse sind möglich.
                                                        Ein nützliches Feature ist die Event-Delegierung, bei der Event-Handler dynamisch auf Elemente angewendet werden können. Das
                                                        erweiterte Event-System von jQuery bietet somit eine leistungsstarke Möglichkeit, Ereignisse auf Webseiten zu verarbeiten.
                                                </p>
                                        </div>
                                </div>
                                <div class="slide">
                                        <div class="carousel-img">
                                                <img src={Animation} alt="Animation und Effekte" />
                                        </div>
                                        <div class="carousel-content">
                                                <h3>Animation und Effekte</h3>
                                                <p>
                                                        Mit jQuery können Animationen und Effekte auf Webseiten erstellt werden, um die Nutzererfahrung zu verbessern. Es gibt eine
                                                        Vielzahl von Funktionen, die es ermöglichen, Elemente auf elegante Weise zu animieren oder Effekte hinzuzufügen.
                                                        Vorgefertigte Effekte wie z.B. Fade-Ins oder Slide-Ins können einfach erzeugt werden. Durch die Verwendung von
                                                        Callback-Funktionen können Animationen und Effekte präzise gesteuert und angepasst werden. Insgesamt bietet jQuery eine
                                                        leistungsstarke Möglichkeit, Animationen und Effekte auf Webseiten zu erstellen und zu steuern.
                                                </p>
                                        </div>
                                </div>
                                <div class="slide">
                                        <div class="carousel-img">
                                                <img src={Ajax} alt="Ajax Funktionalität" />
                                        </div>
                                        <div class="carousel-content">
                                                <h3>Ajax Funktionalität</h3>
                                                <p>
                                                        Ajax ist ein wichtiger Teil von jQuery und ermöglicht es, Inhalte von Webseiten dynamisch zu laden, ohne dass die Seite neu
                                                        geladen werden muss. Mit jQuery können Ajax-Anfragen auf einfache Weise erstellt werden, und es gibt eine Vielzahl von
                                                        Optionen, die für die Ajax-Funktionalität konfiguriert werden können. Insgesamt bietet die Ajax-Funktionalität von jQuery
                                                        eine leistungsstarke Möglichkeit, Inhalte auf Webseiten zu laden und dadurch die Nutzererfahrung zu verbessern.
                                                </p>
                                        </div>
                                </div>
                        </div>
                </section>
        </main>
        <footer>
                <div class="footer-container">
                        <div class="footer-section-01">
                                <h4>Wer?</h4>
                                <ul>
                                        <li>Programmiersprachen 3</li>
                                        <li>Dozent Maurice Rio</li>
                                        <li>Studentin Anja Gutmann</li>
                                </ul>
                        </div>
                        <div class="footer-section-02">
                                <h4>Was?</h4>
                                <ul>
                                        <li>Webdesign</li>
                                        <li>Webentwicklung</li>
                                </ul>
                        </div>
                        <div class="footer-section-03">
                                <h4>Wo?</h4>
                                <ul>
                                        <li>Hochschule für Gestaltung</li>
                                        <li>Rektor-Klaus-Straße 100</li>
                                        <li>73525 Schwäbisch Gmünd</li>
                                        <br />
                                        <li><a href="mailto:anja.gutmann@hfg-gmuend.de">E-Mail: anja.gutmann@hfg-gmuend.de</a></li>
                                </ul>
                        </div>
                </div>
        </footer>

        <script src="script.js"></script>
</body>

<!-- </html> -->

<style>
        * {
                font-family: Poppins, Arial, sans-serif;
                font-weight: 400;
                margin: 0;
        }

        header {
                width: 100vw;
                height: auto;
                overflow-x: hidden;
        }

        body {
                cursor: none;
        }

        main {
                overflow: hidden;
                height: 380em;
        }

        h1:hover span {
                color: blue;
        }

        h1 span {
                transition: color 0.4s ease;
                font-weight: 600;
        }

        h3 {
                font-family: Poppins, Arial, sans-serif;
                font-size: 2.5em;
                font-weight: 600;
                color: white;
                margin-bottom: 0.5em;
        }

        h4 {
                font-family: Poppins, Arial, sans-serif;
                font-size: 2.5em;
                font-weight: 600;
                color: blue;
                margin-bottom: 0.5em;
        }

        p {
                font-family: Poppins, Arial, sans-serif;
                font-weight: 400;
                font-size: 1.3em;
                color: white;
        }

        br {
                line-height: 1em;
        }

        .hover-label {
                position: fixed;
                color: blue;
                font-size: 1em;
                padding: 0.5em 1em;
                z-index: 9998;
                font-weight: 600;
                line-height: 1.3em;
                opacity: 0;
                transform: translateY(-10px);
                transition: opacity 0.25s ease, transform 0.25s ease;
        }

        .hover-label.show {
                display: block;
                opacity: 1;
                transform: translateY(0);
        }

        .cursor {
                position: fixed;
                width: 1.5em;
                height: 1.5em;
                border-radius: 50%;
                background-color: blue;
                transform: translate(-50%, -50%);
                transition: transform 0.3s ease-out;
                pointer-events: none;
                z-index: 9999;
        }

        a:hover,
        button:hover {
                cursor: default;
                cursor: none;
        }

        .site-header-column_left {
                height: 3em;
                width: 3em;
                padding: 1em;
                align-items: center;
        }

        .site-header-column_right {
                padding-right: 1em;
                align-items: center;
        }

        .site-header-home {
                position: relative;
                height: 3em;
                width: 3em;
        }

        .site-header-home img {
                height: 4em;
                width: 4em;
        }

        .site-header-home button {
                border: none;
                position: absolute;
                background-color: white;
                padding: 0;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
        }

        .site-header-logo {
                display: flex;
                float: right;
                width: 150px;
        }

        .site-header-logo img {
                max-width: 100%;
                height: auto;
                float: right;
        }

        .scroll-arrow {
                height: 4em;
                width: 4em;
                position: absolute;
                top: 90%;
                left: 2.5em;
                display: flex;
                justify-content: center;
                z-index: 999;
                margin: 0;
                overflow: hidden;
        }

        .scroll-arrow img {
                height: 4em;
                width: 4em;
        }

        .containerOne {
                box-sizing: border-box;
                position: relative;
                height: 90vh;
                max-width: 100vw;
                padding-left: 7em;
                padding-right: 7em;
        }

        .sectionOne {
                position: relative;
                padding-top: 300px;
        }

        .sectionOne h1 {
                font-family: Poppins, Arial, sans-serif;
                font-weight: 550;
                font-size: 5em;
                margin: 0;
                line-height: 1.3em;
                display: flex-end;
                grid-column: 2 / span 2;
                grid-row: 1 / span 1;
        }

        .sectionOne-kategorie {
                font-family: Poppins, Arial, sans-serif;
                font-size: 1.3em;
                margin-right: 8em;
                color: blue;
                grid-column: 1 / span 1;
                grid-row: 1 / span 1;
        }

        .containerTwo {
                box-sizing: border-box;
                position: relative;
                display: grid;
                grid-template-columns: 1fr 2fr 2fr;
                grid-template-rows: 3fr 3fr 1fr;
                grid-gap: 3em;
                padding: 8em 7em 0 7em;
                width: 100vw;
                height: 100vh;
                background-color: rgb(0, 0, 0);
        }

        .sectionTwo-kategorie {
                font-family: Poppins, Arial, sans-serif;
                font-size: 1.3em;
                color: white;
                grid-column: 1 / span 1;
                grid-row: 1 / span 2;
        }

        /* .sectionTwo-tiles {
    flex-direction: row;
} */

        .containerThree {
                box-sizing: border-box;
                position: relative;
                padding: 7em 7em 0 7em;
                width: 100vw;
                height: 100vh;
                background-color: white;
        }

        .sectionThree-kategorie {
                font-family: Poppins, Arial, sans-serif;
                font-size: 1.3em;
                color: blue;
                grid-column: 1 / span 2;
                grid-row: 1 / span 1;
                margin-bottom: 3em;
        }

        .carousel-content h3 {
                font-family: Poppins, Arial, sans-serif;
                font-size: 2.5em;
                font-weight: 600;
                color: black;
                margin-bottom: 1em;
                grid-column: 2 / span 1;
        }

        .carousel-content p {
                font-family: Poppins, Arial, sans-serif;
                font-weight: 400;
                font-size: 1.3em;
                color: black;
                grid-column: 2 / span 1;
        }

        .carousel-img img {
                max-width: 100%;
                height: auto;
        }

        .carousel-content {
                display: flex;
                width: calc(40% - 3em);
                flex-direction: column;
                float: right;
        }

        .carousel-img {
                display: flex;
                width: calc(60% - 3em);
                float: left;
        }

        .slide .active-slider {
                display: flex;
                flex-direction: column;
        }

        .slide {
                opacity: 0;
                transition: opacity 0.5s ease-in-out;
                grid-column: 1 / span 2;
        }

        .active-slider {
                opacity: 1;
        }

        footer {
                width: 100vw;
                height: auto;
                position: absolute;
                background-color: rgb(250, 250, 250);
                padding: 7em;
                box-sizing: border-box;
        }

        .footer-container {
                display: flex;
                justify-content: space-between;
        }

        .footer-section-01 ul,
        .footer-section-02 ul,
        .footer-section-03 ul {
                padding: 0;
                list-style: none;
                line-height: 2em;
        }

        .footer-section-01 ul li,
        .footer-section-02 ul li,
        .footer-section-03 ul li {
                font-size: 1em;
        }

        .footer-section-01 li {
                font-weight: bold;
                color: blue;
        }

        .footer-section-03 li a {
                font-weight: bold;
                color: blue;
                text-decoration: none;
        }
</style>
