
<script>
    import Pfad from '$lib/img/pfad.png';
    import Groß from '$lib/img/gross.svg';
    import Protokoll from '$lib/img/protokoll.png';
    import Domainname from '$lib/img/domainname.png';
</script>

<div class="site">
        <div class="content">
                
            <head>
                <meta charset="UTF-8">
                <meta http-equiv="X-UA-Compatible" content="IE=edge">
                <meta name="viewport" content="width=device-width, initial-scale=1.0">
                <title>Document</title>
                <link rel="stylesheet" href="fonts/stylesheet.css">
                <link rel="stylesheet" href="css/style.css">
                <link rel="stylesheet" href="css/mobile.css">
                <link rel="stylesheet" href="css/desktop.css">
            </head>
            
            <body>
                <div id="wrapper">
                    <header>
                        <div id="logo"> URL</div>
                        <ul class="nav-links">
                            <li class="nav-item"><a href="/">Home</a></li>
                            <li class="nav-item"><a href="/">Definition</a></li>
                            <li class="nav-item"><a href="/">Examples</a></li>
                            <li class="nav-item"><a href="/">History</a></li>
                        </ul>
                    </header>
                    <img id="gross" src={Groß} alt="Groß"/>
                    <section>
                        <div id="content">
                            <h3>Uniform Resource Locator</h3> <br>
                            <p> Die Abkürzung URL steht für "Uniform Resource Locator", <br> auf Deutsch bedeutet dies "einheitlicher Ressourcenanzeiger". <br> Es handelt sich dabei um einen Standard, mit dem <br> bestimmte Inhalte aufgerufen werden. <br> <br> Die URL
                                ist eine Zeichenkette, die also verwendet wird, <br> um eine bestimmte Ressource im Internet zu identifizieren. <br> Sie enthält Informationen darüber, wo sich die Ressource befindet <br> und wie darauf zugegriffen werden kann. <br>                    Eine URL sieht normalerweise wie folgt aus:
                            </p>
                        </div>
                    </section>
            
                    <article id="protokolltext">
                        <p>
                            <b>Das Protokoll</b> <br> wird für die Kommunikation zwischen <br> dem Client und dem Server verwendet. <br> Andere Protokolle sind zum Beispiel <br> ftp:// mailto:// oder file:// <br> Somit kann man einen Dateiserver <br> über den Browser
                            öffnen, <br> den Befehl für eine Mail an eine <br> bestimmte Adresse geben, sowie <br> eine Datei von Ihrem Computer <br> im Browser öffnen.
                        </p>
                    </article>
                    <img id="protokollbild" src={Protokoll} alt="Protokoll"/>
            
                    <article id="domainnametext">
                        <p>
                            <b>Die Domain</b> <br> sollte jedem bekannt sein. <br> Bei ihr handelt es sich um die <br> Hauptadresse der Webseite, <br> quasi die Eingangstür. <br> Alternativ ist auch die Eingabe <br> der IP-Adresse der Webseite möglich.
                        </p>
                    </article>
                    <img id="domainnamebild" src={Domainname} alt="Donainname"/>
            
                    <article id="pfadtext">
                        <p>
                            <b>Der Pfad</b> <br> führt zur Ressource auf der Website. <br> Manchmal befinden sich tausende Artikel, <br> Fotos, Bilder, Downloads und... darauf. <br> Um den Überblick nicht zu verlieren, <br> haben viele Webseiten ein Verzeichnis,
                            <br> ähnlich wie Ordner auf dem Computer. <br> In dem Verzeichnis, stecken entweder <br> weitere Unterverzeichnisse oder Dateien.
                        </p>
                    </article>
                    <img id="pfadbild" src={Pfad} alt="Pfad"/>
            
            
            
                    <footer>
                        <ul class="impressum">
                            <li class="impressum-item"><a href="/">Impressum</a></li>
                            <li class="impressum-item"><a href="/">FAQs</a></li>
                            <li class="impressum-item"><a href="/">Name</a></li>
                            <li class="impressum-item"><a href="/">Copyrigth</a></li>
                        </ul>
                    </footer>
                </div>
            </body>


        </div>
</div>

<style>

* {
    font-family: "Montserrat", Verdana, sans-serif;
    box-sizing: border-box;
}

@media screen and (min-width: 768px) {
    #wrapper {
        width: windowwidth;
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        grid-template-rows: 60px 312px 440px 300px 300px 300px 60px;
        grid-template-areas: "kopfzeile kopfzeile kopfzeile kopfzeile" "bild bild bild bild" "content content content content" "leer1 bild1 content1 leer2" "leer3 content2 bild2 leer4" "leer5 bild3 content3 leer6" "fusszeile fusszeile fusszeile fusszeile";
    }
    header {
        background-color: #B6C2DF;
        padding-left: 30px;
        padding-right: 10px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        grid-area: kopfzeile;
    }
    #logo {
        display: inline-block;
        font-weight: bold;
        color: white;
    }
    .nav-links {
        list-style: none;
        display: flex;
    }
    .nav-item a {
        display: inline-block;
        padding: 10px 15px;
        text-decoration: none;
        color: white;
    }
    #gross {
        grid-area: bild;
        width: 100%;
    }
    section {
        grid-area: content;
        background-color: #B6C2DF;
    }
    section p,
    h3 {
        text-align: center;
        color: white;
        margin: 0 100px 0 100px;
    }
    #content {
        height: auto;
        margin-top: 100px;
    }
    footer {
        background-color: #B6C2DF;
        grid-area: fusszeile;
        display: flex;
        justify-content: space-between;
        align-items: center;
        justify-content: end;
    }
    #protokolltext {
        grid-area: content1;
        display: flex;
        align-items: center;
    }
    #protokollbild {
        grid-area: bild1;
        display: flex;
        align-self: center;
    }
    #domainnametext {
        grid-area: content2;
        display: flex;
        align-items: center;
    }
    #domainnamebild {
        grid-area: bild2;
        display: flex;
        align-self: center;
    }
    #pfadtext {
        grid-area: content3;
        display: flex;
        align-items: center;
    }
    #pfadbild {
        grid-area: bild3;
        display: flex;
        align-self: center;
    }
    .impressum {
        list-style: none;
        display: flex;
    }
    .impressum-item a {
        display: inline-block;
        padding: 10px 15px;
        text-decoration: none;
        color: white;
    }
}

</style>