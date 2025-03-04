<script lang="ts">
	import Icon from '@iconify/svelte'

	interface Props {
		icon: string
		titlePre: string
		title: string
		description: string
	}

	const { icon, titlePre, title, description } = $props()
</script>

<div>
	<h3 class="flex">
		<Icon {icon} class="text-accent mr-3 size-8 shrink-0 self-center md:mr-6 md:size-10" />
		<span class="self-center">
			<span class="font-light text-neutral-300">{titlePre}</span>
			{title}
		</span>
	</h3>
</div>
