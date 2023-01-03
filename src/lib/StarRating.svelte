<script lang="ts">
	import Star from './Star.svelte';

	export let rating: number = 0;
	export let fillColor: string = 'gold';
	export let emptyColor: string = 'grey';
    export let size: number = 24;

	export let ratingChanged: (rating: number) => void;

	let currentHover: number = 0;

	$: ratingChanged(rating);
</script>

<div class="holder">
	{#each [1, 2, 3, 4, 5] as star}
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<div
			on:click={() => (rating = star)}
			on:mouseenter={() => (currentHover = star)}
			on:mouseleave={() => (currentHover = 0)}
		>
			<Star size={size} color={star <= currentHover ? fillColor : star <= rating ? fillColor : emptyColor} />
		</div>
	{/each}
</div>

<style>
	.holder {
		cursor: pointer;
		display: flex;
		flex-direction: row;
		width: 100%;
		justify-content: center;
		align-items: center;
	}
</style>
