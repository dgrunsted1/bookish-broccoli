<script>
    import Header from './Header.svelte';
    import SideBar from './SideBar.svelte';
    l;
</script>

<main>
   <Header/>
   <SideBar {currPage}/>
   <h1>travel</h1>
</main>

<style>
	main {
		text-align: center;
		margin: 0 auto;
		height: 100%;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
