<script>
	import { writable } from 'svelte/store';

	const scale = writable(1);
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
