<script>
    import CardRating from "./lib/Card-rating.svelte";
    import CardThanks from './lib/Card-Thanks.svelte';

    let isSubmitted = false;
    let rating = 0;

    const handleSubmit = (r) => {
        if(!r) return;
        isSubmitted = !isSubmitted;
        rating = r;
    }
</script>

<!--<button on:click={handleSubmit}>Handle Card</button>-->
<main>
    {#if !isSubmitted}
        <CardRating handleSubmit={handleSubmit} />
    {:else}
        <CardThanks rating={rating} />
    {/if}
</main>

<style>
    main {
        display: flex;
        justify-content: center;
    }
</style>
