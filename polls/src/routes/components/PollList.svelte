<script>
    import Polldetails from "./polldetails.svelte";

    export let polls = []
</script>

<div class="poll-list">
    {#each polls as poll (poll.id)}
        <div>
            <Polldetails {poll} on:vote />
        </div>
    {/each}
</div>

<style>
    .poll-list{
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 20px;
    }

</style>