<script>
    import { fade } from 'svelte/transition';
    export let todo;
</script>

<div transition:fade >
    <p>{todo}</p>
</div>

<style>
    div {
        min-width: 239px;
        height: 43px;
        margin: 20px auto;
        padding-left: 17px;
        width: fit-content;
        background-color: rgba(250, 250, 250, .2);
    }
    p {
        line-height: 43px;
        margin: 0;
    }
</style>