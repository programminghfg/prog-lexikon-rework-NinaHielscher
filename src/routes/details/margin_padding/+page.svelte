<script>
    let navLinks = [
        { label: "Home", url: "#" },
        { label: "Thema1", url: "#" },
        { label: "Thema2", url: "#" },
        { label: "Thema3", url: "#" },
    ];

    let sources = [
        { label: "Quelle1", url: "#" },
        { label: "Quelle2", url: "#" },
        { label: "Quelle3", url: "#" },
    ];
</script>

<div class="header">
    <h1>Wiki</h1>
    <p>Margin & Padding</p>
</div>

<div class="topnav">
    <a href="../../index.html">Home</a>
    <a href="#">Link</a>
    <a href="#">Link</a>
    <a href="#" style="float:right">Link</a>
</div>

<div class="row">
    <div class="leftcolumn">
        <div class="card">
            <h2>Nav Links</h2>
            {#each navLinks as link}
                <p><a href={link.url}>{link.label}</a></p>
            {/each}
        </div>
        <div class="card">
            <h3>Quellen</h3>
            {#each sources as source}
                <p><a href={source.url}>{source.label}</a></p>
            {/each}
        </div>
        <div class="card">
            <h3>Follow Me</h3>
            <p>Alica Hahnau</p>
            <p />
        </div>
    </div>
    <div class="rightcolumn">
        <div class="twomiddle">
            <h2 />
            <h5 />
            <div class="imgpadding" style="height:200px;" />
            <p />
            <p />
        </div>
        <div class="twomiddle">
            <h2>Definition</h2>
            <h5>Die Begriffe Margin und Padding</h5>
            <p>
                stammen aus dem CSS. Mit dessen Hilfe werden die
                unterschiedlichen Elemente wie Text, Überschriften, Links,
                Buttons und Sektionen gestaltet. Eben alle Elemente, aus denen
                deine Homepage besteht.
            </p>
        </div>
        <div class="onemiddle">
            <p>
                Das Boxmodell definiert CSS margin als Abstand, padding als
                Polster und einen Rahmen border um das Element. Margin legt
                einen Abstand gegen benachbarte Elemente fest (z.B. den
                vertikalen Abstand zweier div-Elemente im Layout einer Webseite)
                und auch den Abstand vom umfassenden Element.
            </p>
        </div>
        <div class="threemiddle">
            <h2>Padding</h2>
            <h5>Was ist Padding</h5>
            <p>
                Die CSS-Eigenschaft padding beschreibt den Innenabstand eines
                Elementes zu seinem Rahmen. Die optische Polsterung kann dabei
                für alle vier Seiten des Elementes (top, right, bottom, left)
                festgelegt werden. Die Werte werden meist in Pixeln oder Prozent
                angeben.
            </p>
        </div>
        <div class="threemiddle">
            <div class="imgmargin" style="height:200px;" />
        </div>
        <div class="threemiddle">
            <h2>Margin</h2>
            <h5>Was macht Margin</h5>
            <p>
                Mit Margin können Sie einen einheitlichen Rand/Abstand für oben,
                unten, links und rechts bestimmen. Erlaubt sind ein bis vier
                numerische Angaben. Eine Angabe bedeutet: alle vier Ränder
                erhalten den gleichen Abstand/Rand.
            </p>
        </div>
    </div>
</div>

<div class="footer">
    <h2>Erstellt und Verwaltet von Alica Hahnau&#169</h2>
</div>

<style>
    body {
        font-family: Arial;
        padding: 10px;
        background: #f1f1f1;
    }

    /* Header/Blog Title */
    .header {
        padding: 30px;
        text-align: center;
        background: white;
    }

    .header h1 {
        font-size: 50px;
    }

    /* Style the top navigation bar */
    .topnav {
        overflow: hidden;
        background-color: #333;
    }

    /* Style the topnav links */
    .topnav a {
        float: left;
        display: block;
        color: #f2f2f2;
        text-align: center;
        padding: 14px 16px;
        text-decoration: none;
    }

    /* Change color on hover */
    .topnav a:hover {
        background-color: #ddd;
        color: black;
    }

    /* Create two unequal columns that floats next to each other */
    /* Left column */
    .leftcolumn {
        float: left;
        width: 25%;
        background-color: #f1f1f1;
        padding-right: 20px;
    }

    /* Right column */
    .rightcolumn {
        float: left;
        width: 75%;
    }

    .imgpadding {
        width: 100%;
        padding: 20px;
        background-image: url(./padding.jpeg);
        background-repeat: no-repeat;
        background-size: contain;
    }

    .imgmargin {
        width: 100%;
        padding: 20px;
        background-image: url(./margin.PNG);
        background-repeat: no-repeat;
        background-size: contain;
    }

    /* Add a card effect for articles */
    .card {
        background-color: white;
        padding: 20px;
        margin-top: 20px;
    }

    .twomiddle {
        float: left;
        width: 50%;
        padding: 10px;
    }

    .onemiddle {
        float: left;
        width: 100%;
    }

    .threemiddle {
        float: left;
        width: 33%;
        padding: 10px;
    }

    /* Clear floats after the columns */
    .row::after {
        content: "";
        display: table;
        clear: both;
    }

    /* Footer */
    .footer {
        padding: 20px;
        text-align: center;
        background: #ddd;
        margin-top: 20px;
    }

    /* Responsive layout - when the screen is less than 800px wide, make the two columns stack on top of each other instead of next to each other */
    @media screen and (max-width: 800px) {
        .leftcolumn,
        .rightcolumn,
        .onemiddle,
        .twomiddle,
        .threemiddle {
            width: 100%;
            padding: 0;
        }
    }

    /* Responsive layout - when the screen is less than 400px wide, make the navigation links stack on top of each other instead of next to each other */
    @media screen and (max-width: 400px) {
        .topnav a {
            float: none;
            width: 100%;
        }
    }

    * {
        box-sizing: border-box;
    }

    /* Add more styles for other classes as needed */
</style>
