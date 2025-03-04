<script lang="ts">
	import type { Snippet } from 'svelte'

	interface Props {
		imgURL?: string
		overlay?: boolean
		id: string
		heading?: Snippet
		body?: Snippet
	}

	const { imgURL, overlay, id, heading, body }: Props = $props()
</script>

<div
	class="grid min-h-screen min-w-screen place-items-center bg-cover bg-center"
	style:background-image="url({imgURL})"
>
	{#if overlay}
		<div class="bg-neutral col-start-1 row-start-1 h-screen w-screen opacity-50"></div>
	{/if}

	<div
		class={[
			'z-0 col-start-1 row-start-1 my-24 flex max-w-[60ch] flex-col items-center justify-center',
			overlay &&
				'prose-headings:text-primary prose-a:text-primary prose-a:bg-[url(/src/lib/assets/1x4-00adb5ff.png)] text-center',
		]}
		style="padding: 0 clamp(1rem, 5%, 2rem);"
	>
		<div>
			{@render heading?.()}
		</div>
		<div>
			{@render body?.()}
		</div>
	</div>
</div>
