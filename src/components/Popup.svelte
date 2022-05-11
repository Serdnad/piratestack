<script lang="ts">
    export let src: string
</script>

{#if src}
    <div>
        <img {src} />
    </div>
{/if}

<style lang="scss">
    div {
        transition: all 0.5s;
        animation: open 0.4s;

        z-index: 100;

        margin: auto;
        width: 80vw;
        max-height: 80vh;

        overflow: hidden;
        box-shadow: 0 0 6px 3px #555555aa;

        border-radius: 16px;
    }

    img {
        width: 100%;
        height: 100%;

        object-fit: contain;
        object-position: center;
    }

    @keyframes open {
        0% {
            opacity: 0;
            width: 0;

            transform: translateY(50%);
        }
        100% {
            width: 80vw;
            opacity: 1;
        }
    }
</style>
