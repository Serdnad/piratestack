<script lang="ts">
    import Popup from "./components/Popup.svelte"
    import TextField from "./components/TextField.svelte"

    let input: string = ""

    let word_images = {
        pirates: "/images/clues/pirates.jpg",
        artillery: "/images/clues/cannon.jpg",
        trireme: "/images/clues/atheneum.jpg",
        tropical: "/images/clues/tropical.jpg",
        boulder: "/images/clues/boulder.jpg",
        acid: "/images/clues/acid.jpg",
        ten: "/images/clues/polyhedron.jpg",
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
