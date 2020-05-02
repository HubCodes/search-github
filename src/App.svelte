<script>
    import Header from './Header.svelte';
    import Search from './Search.svelte';
    import Repository from './Repository.svelte';

    let items;

    async function load(event) {
        const { keyword } = event.detail;
        const fetchResult = await fetch(`https://api.github.com/search/repositories?q=${keyword}&sort=stars&order=desc`);
        const content = await fetchResult.json();
        items = content.items;
    }
</script>
<style>
    #page {
        margin-top: 30px;
        display: flex;
        flex-direction: column;
    }
    #repositories {
        margin-top: 50px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>
<div id="page">
    <Header />
    <Search on:message={load} />
    <div id="repositories">
        {#if items}
            {#each items as item, i}
                <Repository {item} />
            {/each}
        {/if}
    </div>
</div>
