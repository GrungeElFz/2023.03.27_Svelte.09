<script>
	import { tweened } from 'svelte/motion';
	import { cubicOut } from 'svelte/easing';

	const scale = tweened(1, {
		duration: 200,
		easing: cubicOut
	});
</script>

<button
	on:click={() => {
		$scale += 1;
	}}
>
	Bigger
</button>
<button
	on:click={() => {
		$scale -= 1;
	}}
>
	Smaller
</button>
<div
	style="
		width: 7rem;
		height: 7rem;
		background-color: rgb(130,115,210);
		transform: scale({$scale});
		transform-origin: 0 0"
/>
