<script>
    import { onMount } from 'svelte';
    
    let data = [];

    onMount(async function() {
        const response = await fetch('https://jsonplaceholder.typicode.com/posts');
        const json = await response.json();
        data = json;
        console.log(data);
    })

</script>

<ul>

    {#each data as {title}}
        <li><p>{title}</p></li>
    {/each}

</ul>