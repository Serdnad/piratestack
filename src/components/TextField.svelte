<script lang="ts">
    export let text: string
</script>

<div>
    <input bind:value={text} />
</div>

<style lang="scss">
    :global(html, body) {
        margin: 0;
        padding: 0;
    }

    div {
        margin: auto;

        display: flex;
        align-items: center;
        justify-content: center;
    }

    input {
        z-index: 100;
        font-size: 40px;
        margin: 32px;
        padding: 16px;
        border-radius: 8px;
        text-transform: uppercase;

        max-width: 80%;

        &:focus {
            outline: none;
        }
    }
</style>
