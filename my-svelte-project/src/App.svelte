<script>
	 import Header from './Header.svelte';
	 import SideBar from './SideBar.svelte';
	 import Article from './Article.svelte';
	 import Wordle from './Wordle.svelte';
	 import PhotographyPage from './PhotographyPage.svelte';
	 let pages = ['wordle', 'travel', 'music', 'sports', 'fashion', 'cooking', 'tech', 'photography'];
	 let currPage = 'home';

	 const tabChange = (e) => {
		 currPage = e.detail;
	 }
</script>

<main>
	<Header on:tabChange={tabChange}/>
	<SideBar {currPage} {pages} on:tabChange={tabChange} />
		{#if currPage == 'travel'}
		<h2>travel</h2>
		{:else if currPage == 'music'}
		<h2>music</h2>
		{:else if currPage == 'sports'}
		<h2>sports</h2>
		{:else if currPage == 'fashion'}
		<h2>fashion</h2>
		{:else if currPage == 'cooking'}
		<h2>Food</h2>
		<Article/>
		{:else if currPage == 'travel'}
		<h2>travel</h2>
		{:else if currPage == 'tech'}
		<h2>tech</h2>
		{:else if currPage == 'photography'}
		<h2>photography</h2>
		<PhotographyPage />
		{:else if currPage == 'wordle'}
		<h2>Wordle</h2>
		<Wordle/>
		{:else}
		<h2>home</h2>
		{/if}
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

	h2 {
		padding-top: 56px;
	}
</style>