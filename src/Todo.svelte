<script>
    import { fade } from 'svelte/transition';
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    const deleteHandler = index => {
        dispatch('delete', index)
    }

    export let todo;
    export let index;
</script>

<div transition:fade >
    <p>{todo}</p>
    <i class='fa fa-trash' on:click={deleteHandler(index)}></i>
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
        display: inline-block;
        margin: 0;
    }

    i {
        padding: 14px 16px;
        float: right;
    }

    i:hover {
        cursor: pointer;
    }
</style>