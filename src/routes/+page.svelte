<script>
        import tiles from '$lib/entries/tiles.js';

        let filteredTiles = tiles;
        let tagList = [];
        let filtersActive = false;

        //einmal alle verfügbaren tags durchgehen und liste erstellen in der jedes tag nur einmal vorkommt
        tiles.forEach((tile) => {
                tile.tags.forEach((tag) => {
                        //duplikate suchen
                        let duplicate = false;

                        tagList.forEach((tagObject) => {
                                if (tagObject.name == tag) {
                                        console.log('doppelt, nicht rein');
                                        duplicate = true;
                                        //wir brauchen nicht weiter checken
                                        //das return springt aus der forEach-schleife
                                        return;
                                }
                        });

                        //wenn nach allen checks ein duplikat ausgeschlossen wurde dann hinzufügen
                        if (!duplicate) {
                                tagList.push({ name: tag, active: false });
                        }
                });
        });

        let toggleFilter = (i) => {
                tagList[i].active = !tagList[i].active;
        };

        //wenn sich filter ändern dann nimm alle tiles die ein tag besitzen, dass in der taglist active==true ist mit in die filtered tiles
        $: {
                filteredTiles = [];
                let activeFilters = 0;
                tagList.forEach((tag) => {
                        if (tag.active) {
                                activeFilters++;
                                filtersActive = true;
                                console.log('activetag!');
                                tiles.forEach((tile) => {
                                        tile.tags.forEach((tagToCheck) => {
                                                if (tagToCheck == tag.name) {
                                                        console.log('success: ' + tagToCheck + '==' + tag.name);
                                                        if (!filteredTiles.includes(tile)) {
                                                                filteredTiles.push(tile);
                                                                filteredTiles = filteredTiles;
                                                                console.log('gibts noch nicht, also rein da');
                                                        }
                                                }
                                        });
                                });
                        }
                        console.log('Neue änderung, neue Tiles: ', filteredTiles);
                        filtersActive = activeFilters > 0 ? true : false;
                });
        }
</script>

<div class="container">
        <h1>Glossar</h1>
        <div class="tags">
                {#each tagList as filter, i}
                        <button class="tag filter" on:click={() => toggleFilter(i)} class:active={filter.active}>
                                {filter.name}
                        </button>
                {/each}
        </div>

        <div class="tile-grid">
                {#if filtersActive}
                        {#each filteredTiles as tile}
                                <a href={'details/' + tile.folder}>
                                        <div class="tile">
                                                <h3>{tile.title}</h3>
                                                <p class="tile-content">{tile.description}</p>
                                                <div class="tags">
                                                        {#each tile.tags as tag}
                                                                <div class="tag">{tag}</div>
                                                        {/each}
                                                </div>
                                        </div>
                                </a>
                        {/each}
                {:else}
                        {#each tiles as tile}
                                <a href={'details/' + tile.folder}>
                                        <div class="tile">
                                                <h3>{tile.title}</h3>
                                                <p class="tile-content">{tile.description}</p>
                                                <div class="tags">
                                                        {#each tile.tags as tag}
                                                                <div class="tag">{tag}</div>
                                                        {/each}
                                                </div>
                                        </div>
                                </a>
                        {/each}
                {/if}
        </div>
</div>

<style>
        .filter:hover {
                color: white;
                background-color: grey;
        }

        .active {
                background-color: rgb(73, 136, 192);
                color: white;
        }

        .tags {
                display: flex;
                width: 100%;
                flex-wrap: wrap;
        }
        .tag {
                display: flex;
                background-color: none;
                padding: 2px 8px;
                border-radius: 8px;
                margin: 4px 8px;
                border: 1px solid grey;
        }
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
