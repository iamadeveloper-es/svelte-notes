<script>
    import { createEventDispatcher } from 'svelte'
    const dispatch = createEventDispatcher()
    let title
    let text
    let done = false
    let alertMssg
    const handleSubmit = () => {
        const newNote = {
            title: title,
            text: text,
            done: done

        };
        dispatch('addNote', newNote);
        title = ''
        text = ''
    };

    console.log(title)
</script>
<div class="form-wrapper">
    <h3>Nueva Nota</h3>
    <form class="form" on:submit|preventDefault={handleSubmit}>
        <input type="text" placeholder="título" bind:value="{title}" required>
        <input type="text" placeholder="texto" bind:value="{text}" required>
        <button type="submit">Crear Nota</button>
        <!-- {#if title.value != '' || text.value != ''}
        <div class="alert">
            <p>{alertMssg}</p>
        </div>
        {/if} -->
    </form>
</div>

<style>
    .form-wrapper{
        width: 100%;
        max-width: 400px;
    }
    .form input[type=text]{
        width: 100%;
        height: 35px;
        padding-left: 10px;
        border-radius: 3px;
    }
</style>