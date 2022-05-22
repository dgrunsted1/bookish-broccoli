<script>
    export let page;
    export let currPage;
    export let expanded;
    
    import Around from './icons/Around.svelte';
    import Basketball from './icons/Basketball.svelte';
    import Cooking from './icons/Cooking.svelte';
    import Diaphragm from './icons/Diaphragm.svelte';
    import Photography from './icons/Photography.svelte';
    import Clothes from './icons/Clothes.svelte';
    import Laptop from './icons/Laptop.svelte';
    import Music from './icons/MusicIcon.svelte';

    function updatePage(newPage){
        window.location.assign("travel.svelte")
    }
</script>


    {#if page=='sports'}
        <div class:expanded>
            <Basketball/>
        </div>
    {:else if page=='travel'}
        <div class="icon {expanded}">
            <Around/>
        </div>
    {:else if page=='food'}
        <div class="icon {expanded}">
            <Cooking/>
        </div>
    {:else if page=='photography'}
        <div class="icon {expanded}">
            <Photography/>
        </div>
    {:else if page=='logo'}
        <div class="icon {expanded}">
            <Diaphragm/>
        </div>
    {:else if page=='fashion'}
        <div class="icon {expanded}">
            <Clothes/>
        </div>
    {:else if page=='tech'}
        <div class="icon {expanded}">
            <Laptop/>
        </div>
    {:else if page=='music'}
        <div class="icon {expanded}">
            <Music/>
        </div>
    {/if}


<