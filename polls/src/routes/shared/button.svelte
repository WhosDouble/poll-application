<script>
    export let type = 'primary';
    export let flat = false
    export let inverse = false

</script>

<button class={type} class:flat={flat} class:inverse={inverse}>
    <slot></slot>
</button>

<style>
    button{
        border: 0;
        cursor: pointer;
        border-radius: 5px;
        padding: 8px 12px;
        font-weight: bold;
        box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
    }
    .primary{
        background: #d91b42;
        color: #eee;
    }
    .secondary{
        background: #45c496;
        color: #eee;
    }
    .flat{
        box-shadow: none;
    }
    .primary.inverse{
        color: #d91b42;
        background: transparent;
        border: 2px solid #d91b42;
    }
    .secondary.inverse{
        color: #45c496;
        background: transparent;
        border: 2px solid #45c496;
    }
</style>