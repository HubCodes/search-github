<script>
    import { createEventDispatcher } from 'svelte';

    let keyword = '';

    const dispatch = createEventDispatcher();

    function dispatchOnSearch() {
        dispatch('message', {
            keyword
        })
    }
</script>
<style>
    div {
        margin-top: 20px;
        text-align: center;
    }
    input {
        font-family: 'Roboto', sans-serif;
        width: fit-content;
        border: none;
        border-bottom: 2px solid #828282;
        text-align: center;
    }
    button {
        border: 1px solid #828282;
        background-color: #ffffff;
    }
</style>
<div>
    <input type="text" bind:value={keyword} />
    <button on:click={dispatchOnSearch}>Search</button>
</div>