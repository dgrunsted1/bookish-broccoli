<script>
    import { createEventDispatcher } from 'svelte'; 
    import LongLogo from './icons/LongLogo.svelte';
    const dispatch = createEventDispatcher() ;
</script>

<div id="header">
    <div id="main_container">
        <a on:click={() => dispatch('tabChange', 'home')}><LongLogo/></a>
    </div>
</div>

<style>
    a {
        line-height: 1.5;
        margin-block-start: 0;
        margin-block-end: 0;
        align-items: flex-end;
        color: white;
    }

    #header {
        display: flex;
        justify-content: center;
        position: fixed;
        width: 100%;
        background-color: white;
        top: 0;
    }
</style>