<script lang="ts">
	import { base } from '$app/paths';
</script>

<div class="column">
	<a href="{base}/default">Unstyled Demo</a>
	<a href="{base}/demo">Styled Demo</a>
</div>

<style>
	.column {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		gap: 1em;
	}
</style>
