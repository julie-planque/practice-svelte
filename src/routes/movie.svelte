<script>
    export let movie;
	let src = "https://image.tmdb.org/t/p/w500" + movie.poster_path;
</script>
<div class="movie-item">
    <img {src} alt="{movie.title}" class="movie-poster" />
</div>
<style>
    .movie-item {

    }
    
    .movie-poster {

    }
    
    .movie-title {}
    </style>