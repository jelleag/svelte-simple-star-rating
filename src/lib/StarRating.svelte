<script>
	import Star from './svgs/Star.svelte';

	export let rating = 0;
	export let fillColor = 'gold';
	export let emptyColor = 'grey';
    export let size = 24;
    export let readOnly = false;

	export let ratingChanged;

	let currentHover = 0;
	let cursor = readOnly ? 'default' : 'pointer';

	$: rating != 0 && !readOnly && ratingChanged(rating);
</script>

<div class={readOnly ? "holder-passive" : "holder"}>
	{#each [1, 2, 3, 4, 5] as star} 
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<div
			on:click={() => (rating = readOnly ? rating : star)}
			on:mouseenter={() => (currentHover = readOnly ? currentHover : star)}
			on:mouseleave={() => (currentHover = readOnly ? currentHover : 0)}
		>
			<Star size={size} color={star <= currentHover ? fillColor : star <= rating ? fillColor : emptyColor} />
		</div>
	{/each}
</div>

<style>
	.holder {
		display: flex;
		flex-direction: row;
		width: auto;
		justify-content: center;
		align-items: center;
		cursor: pointer;
	}
	.holder-passive {
		display: flex;
		flex-direction: row;
		width: auto;
		justify-content: center;
		align-items: center;
		cursor: default;
	}
</style>
