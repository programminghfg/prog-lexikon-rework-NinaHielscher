<script>
    import { onMount } from 'svelte';
    import HomeIcon from '$lib/img/home-icon-silhouette.png';
    import Menu from '$lib/img/menu-offnen.png';
    import Header from '$lib/img/header.jpg';
    import Ablauf from '$lib/img/ablauf.png';
    import Meta from '$lib/img/data.png';
    import Tipp from '$lib/img/idea.png';

    onMount(() => {
        // Code, der nach dem Laden der Komponente ausgeführt werden soll
    });
</script>

<div id="wrapper">
    <header>
        <a href="../../index.html"><img id="home-button" src={HomeIcon} alt="home"></a>
        <a href="../../index.html"><h3>Programmier-Lexikon</h3></a>
        <nav><img id="menu" src={Menu} alt="menu"></nav>
    </header>

    <div id="banner">
        <div class="breadcrumb">
            <div class="breadcrumb__item">Lexikon</div>
            <div class="breadcrumb__item">Repository</div>
        </div>
        <div id="header-background">
            <img id="headerbild" src={Header} alt="menu">
        </div>
        <h2>Repository</h2>
        <article id="intro">Der Begriff Repository steht für <b>Aufbewahrungsort</b> oder <b>Behälter</b>. In der
            Softwaretechnik handelt es sich um eine zentrale Ablage in dem digitale Daten, Dokumente, Objekte und
            Programme mit ihren Metadaten verwaltet werden.</article>
        <button type="button"><b>Erfahre mehr!</b></button>
        
    </div>
    <div id="content">
        <article id="allgemein">
            <h1>Allgemeines</h1>
            <p>Die Basis von Repository Systemen bildet in den meisten Fällen eine Datenbank, die lokal auf einer
                Festplatte, zentral auf einem Server oder verteilt in einem CDN-System organisiert sein kann. Hinzu
                kommen sogenannte Data Dictionaries (Datenwörterbuch, Datenkatalog), die die Darstellungsformen,
                Objektdefinitionen und die Beziehungen zwischen einzelnen Datenobjekten umfassen. Die Datenkataloge
                enthalten nicht etwa die zu speichernden Datensätze und Anwendungsdaten, sondern Informationen über
                diese Daten, sprich Metadaten. Bevor physische Daten gespeichert werden können, muss das
                zugrundegelegte Datenmodell den logischen und konzeptionellen Rahmen definieren. Diese Schemata
                bestimmen, wie die Struktur der Datenbank angelegt ist und wie die Modellierung der Daten erfolgen
                soll.</p>
            <p>In der Softwareentwicklung wurden derartige Datenmodelle zunehmend mit Metadaten ausgezeichnet, um
                Entwicklern einen umfassenden Zugang zu allen relevanten Informationen zu geben. Aus diesen Data
                Dictionaries sind die heutigen Versionsverwaltungssysteme und Repositories entstanden. Mit
                erweiterten Funktionalitäten erlauben sie es, auch eigene Datenmodelle zu bestimmen und verschiedenste
                Schnittstellen und Tools zu nutzen. Je nach Ansatz unterstützen sie Entwickler auch bei der Kreation
                des Quellcodes, dem Testing und der Auslieferung von fertigen Programmen und kombinieren somit
                Datenbanken, Versionsverwaltungen und Entwicklungsumgebungen zu einem Repository, auf das alle
                Projektbeteiligten zugreifen können.</p>
        </article>

        <article id="examples">
            <h1>Arten von Repositories</h1>
            <div id="variants">
                <div id="variante_ablauf">
                    <img id="ablauf" src={Ablauf} alt="ablauf">
                    <p><b>Repository zur Versionsverwaltung</b></p>
                    <p>In der Entwicklung von Games, Software, Apps und anderen IT-Produkten kommen Repositories
                        vielfach zum Einsatz. Die klassische Variante in der Erstellung und Verwaltung von Software
                        wird als Concurrent Versions System (CVS) bezeichnet. Dieses System wurde stetig weiterentwickelt
                        und wird in vielen verschiedenen Repositories wie zum Beispiel Subversion, GitHub oder
                        SourceForge.net verwendet. Das Prinzip besteht darin, dass eine Datei aus dem Repository geladen
                        wird (auschecken), um sie zu bearbeiten und anschließend wieder in das Projektarchiv hochzuladen
                        (einchecken). Jegliche Veränderungen an Dateien werden in einem Protokoll festgehalten und sind
                        einsehbar sowie veränderbar.</p>
                </div>
                <div id="variante_metadaten">
                    <img id="meta" src={Meta} alt="metadata">
                    <p><b>Repository für Metadaten</b></p>
                    <p>Bei komplexen IT-Infrastrukturen werden Repositories dazu benutzt, bestimmte Funktionen und
                        Systembausteine in die Infrastruktur zu integrieren. Sogenannte hochintegrative Systeme erfordern
                        Repositories, die das gesamte System selbst beschreiben und Daten über die informationstechnische
                        Umwelt oder Peripherie enthalten. Muss das System auf Veränderungen reagieren, kann es dies dank
                        eines Metaansatzes, der als 'definieren statt programmieren' beschrieben wird. Denn durch
                        Metadaten-Repositories ist es dem System möglich, auf Veränderungen schnell und unkompliziert zu
                        reagieren, ohne dass für diese Änderungen Quellcode oder Programme geschrieben werden müssen.</p>
                </div>
            </div>
        </article>
    </div>

    <aside>
        <h1>Übersicht</h1>
        <ul style="list-style-type:none;">
            <li>Repository
                <ul style="list-style-type:none;">
                    <li><a href="#allgemein">Allgemeines</a></li>
                    <li><a href="#examples">Arten von Repositories</a></li>
                </ul>
            </li>
        </ul>
    </aside>

    <footer>
        <div id="video">
            <img id="tipp" src={Tipp} alt="tipp">
            <p id="tipptext">Als kleine Hilfestellung habe ich dir <a href="https://www.youtube.com/watch?time_continue=6&v=9A26ybw6tGY&embeds_euri=https%3A%2F%2Fbuiltin.com%2F&source_ve_path=MjM4NTE&feature=emb_title"><b>hier</b></a> noch ein interessantes Erklärvideo verlinkt. Nur für die ganz fleißigen Bienen unter euch. Viel Spaß beim Coden, ihr Stars.</p>
        </div>
        <p id="author">Anna Ligon</p>
    </footer>
</div>

<style>
   * {
    font-family: "Schibsted Grotesk", Arial, sans-serif;
    font-size: 1em;
    box-sizing: border-box;
}

header {
    background-color: lightgrey;
    grid-area: kopfzeile;
    padding: 15px;
}

h3 {
    margin: 0;
}

h2 {
    text-transform: uppercase;
    font-size: 200%;
    color: white;
}

#intro {
    color: white;
}

h1 {
    padding-top: 30px;
    font-size: 1.2rem;
}

button {
    position: absolute;
    margin-left: 70%;
    border: none;
    color: white;
    padding: 15px 50px;
    text-align: center;
    text-decoration: none;
    font-size: 16px;
    cursor: pointer;
}

button:hover {
    background-color: darkgrey;
}

button:active {
    border: solid darkgrey;
}

#home-button {
    height: 33px;
    cursor: pointer;
}

header {
    display: flex;
    justify-content: space-between;
    grid-area: kopfzeile;
}

article {
    position: relative;
    padding-left: 50px;
    width: 90%;
    grid-area: content;
}

#variants {
    text-align: center;
    position: relative;
    margin-bottom: 40px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}

#ablauf,
#meta {
    width: 100px;
    margin-top: 20px;
}

#banner {
    grid-area: banner;
    margin: 0;
    width: 100%;
}

#content {
    grid-area: content;
}

aside {
    grid-area: seite;
    background-color: lightgrey;
    padding-left: 50px;
    padding-right: 20px;
    padding-bottom: 20px;
}

li {
    margin-top: 5px;
}

footer {
    grid-area: fusszeile;
    background-color: rgb(226, 225, 225);
    padding: 50px;
}

#video {
    display: flex;
    justify-content: space-between;
}

#tipp {
    height: 50px;
}

#tipptext {
    margin-left: 20px;
}

a {
    color: black;
    text-decoration: none;
}

a:hover {
    opacity: 0.5;
    transition: 0.8s;
}

a:active {
    opacity: 0.3;
}

#author {
    font-size: smaller;
    color: darkgrey;
    margin-top: 40px;
    text-align: center;
}

#header-background {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    overflow: hidden;
}

#headerbild {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: -1;
}

#banner {
    position: relative;
    padding: 20px;
}

h2 {
    position: relative;
    z-index: 1;
    /* Weitere Styles für die Überschrift */
}

article#intro {
    position: relative;
    z-index: 1;
    /* Weitere Styles für den Artikel */
}

@media screen and (min-width: 900px) {
    #wrapper {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
        grid-template-rows: repeat(auto-fit, minmax(0px, 1fr));
        grid-template-areas:
            "kopfzeile kopfzeile kopfzeile kopfzeile kopfzeile"
            "banner banner banner banner banner"
            "content content content content seite"
            "fusszeile fusszeile fusszeile fusszeile fusszeile";
        gap: 0;
        padding: 0;
    }

    header {
        grid-area: kopfzeile;
    }

    #headerbild {
        width: 100%;
    }

    #banner {
        grid-area: banner;
        width: 100%;
        height: auto;
    }

    #menu {
        display: none;
    }

    .breadcrumb {
        align-items: center;
        display: flex;
        position: absolute;
        padding-left: 50px;
        color: white;
    }

    .breadcrumb__item {
        margin: 0.5rem;
    }

    .breadcrumb__item:not(:last-child)::after {
        right: 0;
        top: 0;
        transform: translate(0.5rem, 0px);
        content: '/';
    }

    h2 {
        margin-top: 20%;
        font-size: 8rem;
        color: white;
    }

    article {
        width: 90%;
        font-size: large;
        position: relative;
        padding-left: 50px;
        width: 90%;
        grid-area: content;
    }

    aside {
        padding-top: 50px;
    }

    #intro {
        color: white;
    }

    #allgemein {
        padding-top: 50px;
    }

    #variants {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }

    #variante_ablauf,
    #variante_metadaten {
        width: 380px;
        margin-top: 30px;
    }
}

</style>
