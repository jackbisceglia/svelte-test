<script>
    export let addTask;

    let form = {
        title: '',
        desc: ''
    }

    const updateForm = (field, value) => {
        form = {...form, [field]: value}
    }

    let resetForm = () => {
        form = {
            title: '',
            desc: ''
        }
    }
</script>

<p>Task Title</p>
<input on:change={(e) => updateForm('title', e.target.value)} class="in" type="text" value={form.title}>
<p>Task Description</p>
<textarea on:change={(e) => updateForm('desc', e.target.value)} value={form.desc} class="in" name="" id="" cols="1" rows="1"></textarea>

<button on:click={() => addTask(form, resetForm)}>Add Task</button>

<style>
    button {
        width: 6rem;
        height: 2rem;
        outline: none;
        border: none;
        border-radius: 0.25rem;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        font-size: 1rem;
        font-weight: 600;
        color: #dddddd;
        background-color: #ff3e00;
        cursor: pointer;
        margin: 0.5rem 0;
    }

    p {
        margin: 0.2rem 0;
    }

    input {
        text-align: center;
        height: 2rem;
    }

    .in {
        outline: #ff3e00;
        border: 1px solid #ff3e00;
        border-radius: 0.35rem;
        min-width: 12rem;
        width: 20%
    }

    textarea {
        text-align: center;
        overflow: hidden;
        min-height: 4rem;
        resize: none;
    }
</style>