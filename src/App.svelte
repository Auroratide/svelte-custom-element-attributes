<svelte:options tag="my-app" />

<main>
	<my-component name="inline" unknown="stuff"></my-component>
	{@html `<my-component name="@html" unknown="stuff"></my-component>`}
</main>
