<script>
    import { onMount } from 'svelte';

    let data;

    onMount(async () => {
        const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');
        data = await response.json();
    });
</script>

<main>
    {#if data}
        ID: {data.id}
        <br>
        Title: {data.title}
        <br>
        Completed: {data.completed}
    {:else}
        <p>Loading...</p>
    {/if}
</main>

<style>
</style>
