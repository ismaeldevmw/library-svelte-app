<script>
	import Detail from './detail/Detail.svelte'
	import Library from './library/Library.svelte'

	let page = 'library'
	let pageArgs = {}
	function handleBookSelect(event) {
		page = 'detail'
		pageArgs = event.detail
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
	{#if page === 'detail'}
		<Detail {...pageArgs} />
	{:else}
		<Library on:book-select={handleBookSelect} />
	{/if}
</main>