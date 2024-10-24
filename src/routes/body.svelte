<script>
    import { onMount } from "svelte";
    import Movie from "./movie.svelte";
    let movies = [];
    let isLoading = false;
    onMount(async () => {
        isLoading = true;
        const options = {
            method: "GET",
            headers: {
                accept: "application/json",
                Authorization:
                    "Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIwNGY4ODJmMjhkOWYyZWE1OTBjNTFlNjRmOTEwOTEwNCIsIm5iZiI6MTcyOTE3MzM2NS41MjE0MDIsInN1YiI6IjVjNjFlM2EyOTI1MTQxMmZjNGZiNzUwMCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.YwgGdZ8smPCbewId4MoGLOmgZK3dz333EuSyiOsmrSo",
            },
        };
        fetch(
            "https://api.themoviedb.org/3/discover/movie?include_adult=false&include_video=false&language=en-US&page=1&sort_by=popularity.desc",
            options,
        )
            .then((response) => response.json())
            .then((response) => {
                console.log(response);
                movies = response.results;
            })
            .catch((err) => console.error(err));
    });
</script>

<div>
    <div class="row">
        {#if movies.length > 0}
            <ul>
                {#each movies as movie }
                    <li class="col-md-4">
                        <Movie {movie} />
                    </li>
                {/each}
            </ul>
        {:else if isLoading}
            <p v-else-if="isLoading">Chargement des films...</p>
        {:else}
            <p v-else>Aucun film trouvé.</p>
        {/if}
    </div>
</div>

<style>
    ul {
        list-style: none;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        padding: 30px 0px;

        li {
            width: 300px;
            margin: 8px;
        }
    }

    .movie-poster {
        width: 300px;
    }
</style>
