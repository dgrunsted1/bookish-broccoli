<script>
	 import Header from './Header.svelte';
	 import SideBar from './SideBar.svelte';
	 import Article from './Article.svelte';
	 import Wordle from './Wordle.svelte';
	 import PhotographyPage from './PhotographyPage.svelte';
	 import HighlightReel from './HighlightReel.svelte';
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
		<HighlightReel />
		{:else if currPage == 'fashion'}
		<h2>fashion</h2>
		{:else if currPage == 'cooking'}
		<Article/>
		{:else if currPage == 'travel'}
		<h2>travel</h2>
		{:else if currPage == 'tech'}
		<h2>tech</h2>
		{:else if currPage == 'photography'}
		<PhotographyPage />
		{:else if currPage == 'wordle'}
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

	main {
		padding-top: 60px;
	}
</style>