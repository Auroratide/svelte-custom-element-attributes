<svelte:options tag="my-component" />

<script>
    export let name

    $: console.log(name)
</script>

<p>Name: {name}</p>
