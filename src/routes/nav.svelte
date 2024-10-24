<nav class="menu-genre text-center">
    <ul class="menu-theme">
      <li>
        <button on:click={() => getMoviesByGenre(genre.science)}>
          <img src={imgAlien} alt="Icône illustrant le dessin animé">
          <span class="theme">Science-fiction</span>
        </button>
      </li>
      <li>
        <button on:click={() => getMoviesByGenre(genre.thriller)}>
          <img src={imgArme} alt="Icône illustrant le dessin animé">
          <span class="theme">Thriller</span>
        </button>
      </li>
      <li>
        <button on:click={() => getMoviesByGenre(genre.romance)}>
          <img src={imgAmour} alt="Icône illustrant le dessin animé">
          <span class="theme">Romantique</span>
        </button>
      </li>
      <li>
        <button on:click={() => getMoviesByGenre(genre.familly)}>
          <img src={imgDessinAnime} alt="Icône illustrant le dessin animé">
          <span class="theme">Famillial</span>
        </button>
      </li>
    </ul>
  </nav>
<script>
    import { selectedGenre } from '$lib/stores.js';
    import imgDessinAnime from '$lib/assets/dessin-anime.png';
    import imgAlien from '$lib/assets/alien.png';
    import imgArme from '$lib/assets/arme.png';
    import imgAmour from '$lib/assets/amour.png';
    let genre = {
        familly: 10751,
        science: 878,
        thriller: 53,
        romance: 10749
    }

    function getMoviesByGenre(id_genre) {
        selectedGenre.set(id_genre);
    }

</script>
<style>
    .menu-genre {
      padding: 1rem 0;
      background-color: #25211e;
    }
    ul {
      display: flex;
      gap: 2rem;
      list-style: none;
      padding: 45px 0;
      margin: 0;
      justify-content: center;
    }
    button {
      background: none;
      border: none;
      padding: 0;
      cursor: pointer;
    }
    li button {
      display: flex;
      align-items: center;
      flex-direction: column;
      gap: 0.5rem;
      color: #e0e0e0;
      font-weight: bold;
    }
    li img {
      width: 60px;
      height: 60px;
      object-fit: cover;
      filter: grayscale(40%);
    }
    .theme {
      color: #d2ae12;
      font-weight: 700;
    }
    </style>
