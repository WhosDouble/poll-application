<script>
    import { createEventDispatcher } from "svelte";
    let dispatch = createEventDispatcher()
    
    export let items;
    export let activeItem;
</script>

<div class="tabs">
    <ul>
        {#each items as item}
            <li on:click={() => dispatch('tabChange', item)}>
                <div class:active={item === activeItem}>
                    {item}
                </div>
            </li>
        {/each}
    </ul>
</div>

<style>
    .active{
        color: #d91b42;
        border-bottom: 2px solid #d91b42;
        padding-bottom: 8px;
    }
    .tabs{
        margin-bottom: 40px;
    }
    ul{
        display: flex;
        justify-content: center;
        padding: 0;
        list-style-type: none;
        gap: 20px;
        font-size: 20px;
        cursor: pointer;
    }
</style>