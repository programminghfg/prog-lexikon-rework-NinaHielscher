<script>
        import tiles from '$lib/entries/tiles.js';
</script>

<div class="container">
        <h1>Glossar</h1>
</div>

<style>
        .container {
                padding: 20px;
                min-height: 85vh;
        }

        .tile-grid {
                display: grid;
                gap: 10px;
                grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
        }

        .tile {
                border-radius: 0.5em;
                color: black;
                background-color: rgb(226, 226, 226);
                position: relative;
                transition: all 0.1s ease-in;
                cursor: pointer;
        }

        .tile:hover {
                background-color: rgb(177, 201, 231);
        }

        .tile-content {
                padding: 1em;
        }

        .tile h3 {
                color: black;
                background-color: rgb(187, 187, 187);
                border-radius: 0.5em 0.5em 0 0;
                margin: 0;
                line-height: 50px;
                padding: 0 1em;
        }
</style>
