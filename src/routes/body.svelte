<script>
    import { selectedGenre } from '$lib/stores.js';
    import { writable } from 'svelte/store';
    import Movie from "./movie.svelte";

    export const movies = writable([]);
    let isLoading = false;
    let selectedGenreId;

    $: selectedGenreId = $selectedGenre;
    $: if (selectedGenreId !== null) {
        fetchMovies(selectedGenreId);
    } else {
        fetchMovies();
    }

    async function fetchMovies(genreId = null) {
    isLoading = true;
    movies.set([]);

    const options = {
        method: 'GET',
        headers: {
            accept: 'application/json',
            Authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIwNGY4ODJmMjhkOWYyZWE1OTBjNTFlNjRmOTEwOTEwNCIsIm5iZiI6MTcyOTc3OTE5MS44MTgzNzMsInN1YiI6IjVjNjFlM2EyOTI1MTQxMmZjNGZiNzUwMCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.RlW15Nrp68MA8PKHKFMLUdaE5Me5yYuqu13ooC6GHU4'
        }
    };

    let url = genreId
        ? `https://api.themoviedb.org/3/discover/movie?include_adult=false&include_video=false&language=en-US&page=1&sort_by=popularity.desc&with_genres=${genreId}`
        : 'https://api.themoviedb.org/3/movie/top_rated?language=en-US&page=1';

    try {
        const response = await fetch(url, options);
        const data = await response.json();
        if (data.results && data.results.length > 0) {
            movies.set(data.results);
        } else {
            movies.set([]);
        }
    } catch (err) {
        console.error('Error fetching movies:', err);
    } finally {
        isLoading = false;
    }
}
</script>

<div>
    <div class="row">
        {#if $movies.length > 0}
            <ul class="movie-list">
                {#each $movies as movie}
                    <li class="col-md-4 movie">
                        <Movie {movie} />
                    </li>
                {/each}
            </ul>
        {:else if isLoading}
            <p>Chargement des films...</p>
        {:else}
            <p>Aucun film trouvé.</p>
        {/if}
    </div>
</div>
<style>
    .movie-list {
        list-style: none;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        padding: 30px 0px;

        .movie {
            width: 300px;
            margin: 8px;
        }
    }
</style>
