<script>
	import Library from './library/Library.svelte'

	function handleBookSelect(event) {
		console.log("clicked", event.detail.id)
	}
</script>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

<main>
	<Library on:book-select={handleBookSelect} />
</main>