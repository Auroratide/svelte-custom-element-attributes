Templated from https://github.com/sveltejs/template.

## Input

Let's say you are using Svelte to create a web component, as in `MyComponent.svelte`:

```
<svelte:options tag="my-component" />

<script>
    export let name
</script>

<p>Name: {name}</p>
```

And then, you want to use this component from another Svelte component, as in `App.svelte`:

```
<main>
	<my-component name="inline" unknown="stuff"></my-component>
	{@html `<my-component name="@html" unknown="stuff"></my-component>`}
</main>
```

## Output

This results in the following HTML being generated:

```html
<main>
    <my-component unknown="stuff"></my-component>
    <my-component name="@html" unknown="stuff"></my-component>
</main>
```

And additionally, a console warning:

```
<my-component> was created without expected prop 'name'
```

In other words, the attribute becomes stripped from the web component, and in a tick it seems the component lacks the `name` prop it requires, even though on the next tick `name` will become defined.