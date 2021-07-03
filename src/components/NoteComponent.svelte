<script>
    export let title, text, status

</script>
<div class="note">
    <div class="note-title">
        <h4>{title}</h4>
    </div>
    <div class="note-text">
        <p>{text}</p>
    </div>
    <div class="note-status">
        <span>{status}</span>
    </div>
</div>

<style>
    .note{
        width: 20%;
        margin: 1rem;
        padding: 1rem;
        background-color: #e6e6e6;
        border-radius: 5px;
        overflow: hidden;
    }
</style>