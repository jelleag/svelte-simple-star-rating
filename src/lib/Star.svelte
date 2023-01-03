<script lang="ts">
	export let color: string = 'grey';
	export let size: number = 24;
</script>

<svg
	width={size}
	height={size}
	viewBox={`0 0 24 24`}
	fill="none"
	xmlns="http://www.w3.org/2000/svg"
>
	<path
		d="M12 17.27L18.18 21L16.54 14.35L22 9.24L15.45 8.76L12 2.5L8.55 8.76L2 9.24L7.45 14.35L5.82 21L12 17.27Z"
		fill={color}
	/>
</svg>
