<script>
    export let movie;
    console.log(movie + 'HEY');
	let src = "https://image.tmdb.org/t/p/w500" + movie.poster_path;
    console.log(movie);
    
</script>
<div class="movie-item">
    <img {src} alt="{movie.title}" class="movie-poster" />
</div>
<style>
    .movie-item {
      /* Styles for the movie item container */
    }
    
    .movie-poster {
      /* Styles for the movie poster image */
    }
    
    .movie-title {}
    </style>