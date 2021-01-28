<script>
    export let listItem;
    export let description;
    export let id;

    export let handleDelete;
</script>

<div class="to-do-div">
    <h3>{listItem}</h3>
    <p>{description}</p>
    <button on:click={() => handleDelete(id)} class="delete">
        delete
    </button>
</div>

<style>
    .to-do-div {
        text-align: center;
        width: 25%;
        min-width: 14rem;
        min-height: 2.5rem;
        height: auto;
        background-color: #ffa081;
        border-radius: 0.25rem;
        color: rgb(43, 43, 43);
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-top: 0.5rem;
        margin: 0.75rem 0;
    }

    button {
        width: 30%;
        height: 1.5rem;
        outline: none;
        border: none;
        border-radius: 0.25rem;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        font-size: 1rem;
        font-weight: 600;
        color: #ff3e00;
        background-color: rgb(236, 236, 236);
        cursor: pointer;
        margin: 0.5rem 0;
    }

    h3 {
        font-size: 1.75rem;
        margin: 0;
        max-width: 90%;
    }

    p {
        margin: 0.35rem 0;
        width: 80%;
    }
</style>