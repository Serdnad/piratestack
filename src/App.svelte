<script lang="ts">
    import Popup from "./components/Popup.svelte"
    import TextField from "./components/TextField.svelte"

    let input: string = ""

    let word_list = ["pirate"]

    let word_images = {
        pirate: "/images/pirate.jpg",
    }

    $: image = word_images[input]
</script>

<main>
    <video autoplay muted loop>
        <source src="/ocean.webm" type="video/mp4" />
    </video>

    <div>
        <TextField bind:text={input} />

        <Popup src={image} />
    </div>
</main>

<style lang="scss">
    main {
        background: url("/images/ocean.webm");
        background-position: center;

        min-height: 100vh;

        video {
            z-index: -1;
            position: absolute;

            width: 100vw;
            height: 100vh;
            object-fit: cover;
        }

        div {
            z-index: 10;
        }
    }
</style>
