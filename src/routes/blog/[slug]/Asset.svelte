<script lang="ts">
	export let src: string;
	export let description: string;
</script>

{#if src}
	<img
		loading="lazy"
		src={`${src}?w=1920&h=960`}
		srcset={`${src}?w=3840&h=1920 1920w, ${src}?w=1920&h=960 1280w, ${src}?w=1280&h=640 640w`}
		alt={description ?? ''}
	/>
{/if}