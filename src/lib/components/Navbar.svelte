<script lang="ts">
	import { page } from '$app/state'
	import { onMount } from 'svelte'
	import Icon from '@iconify/svelte'

	const currentPath = page.url.pathname

	// Make typescript happy
	let id: HTMLDialogElement
	onMount(() => {
		id = document.getElementById('fullscreen_menu') as HTMLDialogElement
	})
</script>

<header class={['navbar bg-neutral text-primary fixed top-0 bottom-auto z-50']}>
	<div class="navbar-start">
		<button onclick={() => id.showModal()} class="btn btn-square btn-ghost">
			<Icon icon="ci:hamburger-lg" class="text-2xl" />
		</button>
	</div>
	<div class="navbar-end">
		<a href="/" class="btn btn-ghost text-xl">Southern MN TCT</a>
	</div>
</header>
