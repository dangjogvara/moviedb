<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/popular?api_key=dff69ae49c24386e306a3ba06a0994c9&language=en-US&page=1`
		);
		const data = await res.json();
		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<script>
	import PopularMovies from '../components/PopularMovies.svelte';

	export let popular;
</script>

<!-- API KEY dff69ae49c24386e306a3ba06a0994c9 -->

<section>
	<PopularMovies {popular} />
</section>
