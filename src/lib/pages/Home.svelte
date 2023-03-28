<script>
	import { tweened } from 'svelte/motion';
	import { cubicOut } from 'svelte/easing';

	const size = tweened(
		{
			width: 100,
			height: 100
		},
		{
			duration: 200,
			easing: cubicOut
		}
	);
</script>

<button
	on:click={async () => {
		await size.set({
			width: Math.random() * 500,
			height: Math.random() * 500
		});
		console.log('Done');
	}}
>
	Random Size
</button>

<div
	style="
		width: {$size.width}px;
		height: {$size.height}px;
		background-color: rgb(130,115,210);"
/>
