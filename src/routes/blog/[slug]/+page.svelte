<script lang="ts">
	import { RichTextRenderer } from '@caisy/rich-text-svelte-renderer';
	import DocumentLink from './DocumentLink.svelte';
	export let data: { title: string; text: any };
	console.log(data, JSON.stringify(data));
</script>

<svelte:head>
	<title>{data.title}</title>
</svelte:head>

<section class="max-w-prose">
	<h1>{data.title}</h1>
	{#if data.text && data.text.json}
		<RichTextRenderer
			node={data.text.json}
			overwrites={{ documentLink: DocumentLink }}
			connections={data?.text?.connections}
		/>
	{/if}
</section>

<style>
</style>
