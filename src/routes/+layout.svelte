<script>
        import '../app.css';
</script>

<header>
        <a href="/">
                <h1>Prog3 Lexikon</h1>
        </a>
        <nav>
                <ul>
                        <li><a href="#">About Me</a></li>
                        <li><a href="#">Contact</a></li>
                        <li><a href="#">Portfolio</a></li>
                </ul>
        </nav>
</header>

<slot />

<style>
        nav {
                background-color: rgb(39, 75, 107);
                border-radius: 4px;
                padding-left: 20px;
        }
        a {
                color: white;
        }

        nav ul {
                list-style: none;
                padding: 0;
                height: 32px;
        }

        nav ul li {
                display: inline;
                height: 100%;
                justify-content: center;
                padding-right: 1em;
        }

        header {
                height: 100px;
                padding: 20px;
                background-color: rgb(27, 60, 88);
                color: white;
        }

        header h1 {
                margin: 0;
        }
</style>
