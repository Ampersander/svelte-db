<script>

    export let elements;
    import {onMount} from 'svelte';

    onMount(async () => {
        const res = await fetch("books.json");
        elements =  await res.json();
    });
</script>