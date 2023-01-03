<script>
	import StarRating from '$lib/StarRating.svelte';
</script>

<StarRating ratingChanged={(rating) => console.log(rating)} />
