<script>
import NoteComponent from "./NoteComponent.svelte";
import From from './FormNewNoteComponent.svelte'
import FormNewNoteComponent from "./FormNewNoteComponent.svelte";
    
    let notes = [
        {
            title: 'Aprender Svelte',
            text: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos et hic magnam perferendis deserunt non rem esse aspernatur debitis at, iusto animi possimus doloremque. Sed temporibus ad eius odit quo!',
            done: false
        },
        {
            title: 'Crear Componente',
            text: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos et hic magnam perferendis deserunt non rem esse aspernatur debitis at, iusto animi possimus doloremque. Sed temporibus ad eius odit quo!',
            done: false
        },
        {
            title: 'Aplicación de notas',
            text: 'Lorem ipsum, dolor ',
            done: false
        }
    ];
    const addNewNote = (e) => {
        console.log(e.detail)
        notes.push(e.detail)
        notes = notes
        
    }
</script>
<div>
    <FormNewNoteComponent on:addNote={addNewNote}></FormNewNoteComponent> 
    <ul class="notes">
        {#each notes as note}
        <NoteComponent title="{note.title}" text="{note.text}" status="Estado: {note.done}"></NoteComponent>
        {/each}
    </ul>
</div>

<style>
    .notes{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }
</style>