<script lang="ts">
    import Popup from "./components/Popup.svelte"
    import TextField from "./components/TextField.svelte"

    let input: string = ""

    let word_images = {
        pirates: '/images/clues/PIRATES.jpg"',
        artillery: "/images/clues/ARTILLERY.jpg",
        trireme: "/images/clues/TRIREME.jpg",
        tropical: "/images/clues/TROPICAL.jpg",
        boulder: "/images/clues/BOULDER.jpg",
        acid: "/images/clues/ACID.jpg",
        arrrghten: "/images/clues/ARRRGHTEN.jpg",
        mutiny: "/images/clues/MUTINY.jpg",
        krebs: "/images/clues/KREBS.jpg",
    }

    $: image = word_images[input.toLowerCase()]
</script>

<svelte:head>
    <title>Pirates The Stack</title>
</svelte:head>

<main>
    <div>
        <img src="/images/logo.png" />
        <Popup src={image} />
        <TextField bind:text={input} />
    </div>
</main>

<style lang="scss">
    main {
        min-height: 100vh;

        background: url("/images/background.jpg");
        background-position: center;
        background-size: cover;

        display: flex;
        flex-direction: column-reverse;

        div {
            z-index: 10;
        }

        img {
            position: absolute;
            top: 16px;
            right: 16px;

            max-width: 60%;
        }
    }
</style>
