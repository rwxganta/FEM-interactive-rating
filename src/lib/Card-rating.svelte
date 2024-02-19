<script>
    export let handleSubmit;
    export let rating;
</script>

<article class="card">
    <span class="card__image"></span>
    <h1>How did we do?</h1>
    <p>
        Please let us know how we did with your support request. All feedback is
        appreciated to help us improve our offering!
    </p>

    <form>
        <div class="checklist">
            <input type="radio" name="rating" id="1" value='1' bind:group={rating} />
            <input type="radio" name="rating" id="2" value='2' bind:group={rating} />
            <input type="radio" name="rating" id="3" value='3' bind:group={rating} />
            <input type="radio" name="rating" id="4" value='4' bind:group={rating} />
            <input type="radio" name="rating" id="5" value='5' bind:group={rating} />
        </div>
        <button on:click={() => handleSubmit(rating)}>Submit</button>
    </form>
</article>

<style>
    article {
        display: grid;
        gap: 1.2rem;
    }

    .card__image {
        display: inline-block;
        width: 2.3rem;
        aspect-ratio: 1;
        background-color: var(--Very-Dark-Blue);
        background-image: url("../assets/icon-star.svg");
        background-repeat: no-repeat;
        background-size: 0.8rem;
        background-position: center;
        border-radius: 50%;
    }

    h1 {
        margin: 0;
        font-size: 1.5rem;
    }

    p {
        margin: 0;
        color: var(--Medium-Grey);
    }

    /*ul {
        margin: 0;
        padding: 0;
        list-style: none;
        display: flex;
        justify-content: space-between;

        & button {
            width: 2.7rem;
            aspect-ratio: 1;
            color: var(--Medium-Grey);
            border-radius: 50%;
            display: grid;
            place-content: center;
        }
    }*/

    form {
        display: grid;
        gap: 1.2rem;
    }

    .checklist {
        display: flex;
        justify-content: space-between;
    }

    input[type="radio"] {
        appearance: none;
        margin: 0;
        width: 2.7rem;
        aspect-ratio: 1;
        color: var(--Medium-Grey);
        border-radius: 50%;
        background-color: var(--Very-Dark-Blue);
        cursor: pointer;
        position: relative;
    }

    input[type="radio"]:hover {
        color: var(--White);
        background-color: var(--Light-Grey);
    }


    input[type="radio"]:checked {
        color: var(--White);
        background-color: var(--Orange);
    }


    input[type="radio"]::before {
        content: attr(value);
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        font-size: 1.2rem;
    }

    form button {
        padding-block: 0.8rem;
        font-weight: 700;
        text-transform: uppercase;
        letter-spacing: 1px;
        background-color: var(--Orange);
        border-radius: 100vh;
    }
</style>
