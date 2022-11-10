<!-- TODO: componetizar -->
<!-- TODO: cambiar remarkable a @haakonmb/markdown-draft-js y estilar output -->
<style>
	main {
		background: #0c1618;
		margin: 0;
		padding: 2rem;
		width: 100vw;
		height: 100vh;
		display: flex;
		flex-direction: row;
		gap: 2rem;
	}

	textarea {
		background: #004643;
		width: calc(100vw / 2);
		border-radius: 0.3rem;
		color: #fff;
		padding: 1rem;
		font-size: 1rem;
		border: 2px solid #faf4d3;
		outline: #faf4d3;
		resize: none;
	}

	pre {
		background: #85756e;
		width: calc(100vw / 2);
		border-radius: 0.3rem;
		color: #fff;
		padding: 1rem;
		white-space: pre-wrap;
		overflow-y: scroll;
	}
</style>

<script>
	import { Remarkable } from 'remarkable';

	const iframe = document.createElement('iframe');

	var md = new Remarkable('full', {
		html: true,
		typographer: true,
	});
	let value = '';

	$: output = `${md.render(value)}`;
</script>

<main>
	<!-- <Editor /> -->
	<textarea
		name="editor"
		id="editor"
		cols="100"
		rows="10"
		spellcheck="true"
		bind:value></textarea>

	<!-- <Output value=/> -->
	<pre>{@html output}</pre>
</main>
