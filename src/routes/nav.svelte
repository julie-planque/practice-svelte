<script>
    import { selectedGenre } from "$lib/stores.js";
    import imgDessinAnime from "$lib/assets/dessin-anime.png";
    import imgAlien from "$lib/assets/alien.png";
    import imgArme from "$lib/assets/arme.png";
    import imgAmour from "$lib/assets/amour.png";
    let genre = {
        familly: 10751,
        science: 878,
        thriller: 53,
        romance: 10749,
    };

    function getMoviesByGenre(id_genre) {
        selectedGenre.set(id_genre);
    }
</script>

<nav class="navbar-genre text-center">
    <ul class="genre-menu">
        <li class="genre">
            <button on:click={() => getMoviesByGenre(genre.science)}>
                <img src={imgAlien} alt="Icône alien" />
                <span class="theme">Science-fiction</span>
            </button>
        </li>
        <li class="genre">
            <button on:click={() => getMoviesByGenre(genre.thriller)}>
                <img src={imgArme} alt="Icône pistolet" />
                <span class="theme">Thriller</span>
            </button>
        </li>
        <li class="genre">
            <button on:click={() => getMoviesByGenre(genre.romance)}>
                <img src={imgAmour} alt="Icône coeur" />
                <span class="theme">Romantique</span>
            </button>
        </li>
        <li class="genre">
            <button on:click={() => getMoviesByGenre(genre.familly)}>
                <img
                    src={imgDessinAnime}
                    alt="Icône illustrant le dessin animé"
                />
                <span class="theme">Famillial</span>
            </button>
        </li>
    </ul>
</nav>

<style>
    .navbar-genre {
        padding: 1rem 0;
        background-color: #25211e;
    }
    .genre-menu {
        display: flex;
        gap: 2rem;
        list-style: none;
        padding: 45px 0;
        margin: 0;
        justify-content: center;
    }
    .genre button {
        background: none;
        border: none;
        padding: 0;
        cursor: pointer;
    }
    .genre button:hover {
        img {
            border-radius: 50%;
            border-color: #ffcf00;
            box-shadow: 0 0 10px rgb(255 207 0);
        }
        span {
            color: #ffcf00;
        }
    }
    .genre button {
        display: flex;
        align-items: center;
        flex-direction: column;
        gap: 0.5rem;
        color: #e0e0e0;
        font-weight: bold;
    }
    .genre img {
        width: 60px;
        height: 60px;
    }
    .theme {
        color: #ffcf00;
        font-weight: 700;
    }
</style>
