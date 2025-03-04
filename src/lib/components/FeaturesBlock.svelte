<script lang="ts">
	import type { Snippet } from 'svelte'
	import IconBlock from './IconBlock.svelte'
	import type Icon from '@iconify/svelte'

	const d = [
		{
			title: 'title',
			titlePre: 'titlePre',
			description: 'desc',
			icon: 'bx:bible',
		},
		{
			title: 'title',
			titlePre: 'titlePre',
			description: 'desc',
			icon: 'bx:bible',
		},
	]

	interface Data {
		title: string
		titlePre: string
		description: string
		icon: string
	}

	interface Props {
		id: string
		data: Data[]
		featureSide?: 'left' | 'right'
		heading: Snippet
	}

	const { id, data, featureSide, heading }: Props = $props()

	console.log(featureSide)
</script>

<div class="bg-secondary grid min-h-screen min-w-screen place-items-center bg-cover bg-center" {id}>
	<div class="my-24 grid max-w-[90%] gap-12 md:grid-cols-2">
		<div
			class={[
				'z-0 flex max-w-[60ch] items-center gap-4 py-4 md:justify-center md:px-4 md:text-center',
				featureSide === 'left' && 'order- md:order-2',
			]}
		>
			{@render heading()}
		</div>
		<div class={['mx-auto my-auto space-y-6', featureSide === 'left' && 'order-2 md:order-1']}>
			{#each data as { title, titlePre, description, icon }}
				<IconBlock {icon} {titlePre} {title} {description} />
			{/each}
		</div>
	</div>
</div>
