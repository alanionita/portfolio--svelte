<script lang="ts">
	import Segment from '../../molecules/Segment/+index.svelte';
	export let postHtml: string = '';
	import hljs from 'highlight.js/lib/core';
	import javascript from 'highlight.js/lib/languages/javascript';
	import yaml from 'highlight.js/lib/languages/yaml';
	import shell from 'highlight.js/lib/languages/shell';
	import { onMount } from 'svelte';

	onMount(() => {
		hljs.registerLanguage('javascript', javascript);
		hljs.registerLanguage('yaml', yaml);
		hljs.registerLanguage('shell', shell);
		hljs.highlightAll();
	});
</script>

<Segment class="secondary no-padding">
	<section class="content">
		{@html postHtml}
	</section>
</Segment>

<style>
	.content {
		margin: 6rem 0 0 0;
		padding: 0;
		width: 100%;
		color: var(--color-text);
		font-size: var(--fluid-type-post);
	}

	/* Custom Svelte way to style these dynamically generated @html elements */
	.content :global(blockquote) {
		display: block;
		border-width: 2px 0;
		border-style: solid;
		border-color: #eee;
		padding: 1rem 2rem 0.5em;
		margin: 1rem 0rem 1rem 3rem;
		position: relative;
		color: var(--color-primary);
		font-size: var(--fluid-type-post);
		font-weight: 700;
		font-style: italic;
		background-color: var(--color-accent);
	}

	/* Custom Svelte way to style these dynamically generated @html elements */
	.content :global(blockquote:before) {
		content: '\201C';
		position: absolute;
		top: 0em;
		left: 50%;
		transform: translate(-50%, -50%);
		background: var(--color-primary);
		width: 3rem;
		height: 2rem;
		font: 3rem 'PT Sans', sans-serif;
		color: var(--color-text);
		text-align: center;
	}

	/* Custom Svelte way to style these dynamically generated @html elements */
	.content :global(h2),
	.content :global(h3),
	.content :global(h4) {
		width: 75%;
		text-align: left;
		font-weight: bold;
		font-size: var(--fluid-type);
		line-height: 1.2em;
	}

	/* Custom Svelte way to style these dynamically generated @html elements */
	.content :global(ul) {
		margin: 0;
		padding: 0;
		padding-left: 5%;
		width: 75%;
		color: var(--color-text);
		list-style-type: disc;
		text-align: left;
		font-weight: bold;
		font-size: var(--fluid-type-post);
		font-weight: 400;
	}
</style>
