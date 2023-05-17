<a href="/">Home</a>
<div class="site">
        <div class="content">
                <div class="top">
                        <h1>@media-Queries</h1>
                </div>
                <h2>Was ist @media-Queries?</h2>
                <p>@media-Queries ist ein CSS-Konzept, das es ermöglicht, das Aussehen und Layout einer Webseite basierend auf der Größe des Viewports des Geräts zu ändern.</p>

                <h2>Wie funktionieren @media-Queries?</h2>
                <p>
                        Mit @media-Queries können Entwickler*innen CSS-Regeln für spezifische Viewport-Größen definieren, sodass eine Webseite auf unterschiedlichen Geräten
                        unterschiedlich dargestellt wird. Die CSS-Regeln werden aufgerufen, sobald die Breite des Viewports eine bestimmte Grenze erreicht. So können beispielsweise
                        bestimmte Styles für Smartphones, Tablets und Desktop-Computer definiert werden.
                </p>

                <h2>Beispiel</h2>
                <p>Ein Beispiel für die Verwendung von @media-Queries könnte wie folgt aussehen:</p>

                <div class="code-container">
                        <pre>
            <code>
                &#64media only screen and (max-width: 600px) &#123;
                body &#123;
                background-color: red;
                &#125;
                &#125;
            </code>
        </pre>
                </div>

                <p>In diesem Beispiel wird die Hintergrundfarbe der Webseite auf Rot geändert, wenn die maximale Breite des Viewports 600px beträgt.</p>

                <h2>Zusammenfassung</h2>
                <p>
                        @media-Queries ist ein unverzichtbares Konzept für die Erstellung von responsiven Webseiten, die auf verschiedenen Geräten eine optimale Darstellung und
                        Bedienbarkeit bieten sollen.
                </p>
        </div>
</div>

<style>
        * {
                margin: 0;
                padding: 0;
                box-sizing: border-box;
        }
        .top {
                background-color: #333;
                color: #fff;
                padding: 1rem;
                width: 100vw;
        }
        /* Fonts */
        @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

        * {
                font-family: 'Roboto', sans-serif;
        }
        /* Colors */
        :root {
                --primary-color: #007acc;
                --secondary-color: #5bc0de;
                --tertiary-color: #ff7900;
        }
        /* Responsive Styles */
        @media (max-width: 900px) {
                /* Tablets */
                .site {
                        max-width: 90%;
                }
        }

        @media (max-width: 600px) {
                /* Mobile */
                .site {
                        max-width: 100%;
                        padding: 0 1rem;
                }
        }

        .top {
                background-color: #333;
                color: #fff;
                padding: 1rem;
        }

        .content {
                display: flex;
                flex-wrap: wrap;
                justify-content: space-between;
                padding: 1rem;
        }

        @media (max-width: 600px) {
                /* Mobile-Ansicht */
                .site {
                        grid-template-rows: auto 1fr auto;
                        grid-template-columns: 1fr;
                }
        }

        .site {
                display: grid;
                grid-template-rows: auto 1fr auto;
                grid-template-columns: 1fr;
                min-height: 100vh;
        }

        @media (max-width: 600px) {
                /* Mobile-Ansicht */
                .site {
                        grid-template-rows: auto 1fr auto;
                        grid-template-columns: 1fr;
                }
        }
</style>
