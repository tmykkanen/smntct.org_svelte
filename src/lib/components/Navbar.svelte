<script lang="ts">
	import { page } from '$app/state'
	import FullscreenMenu from './FullscreenMenu.svelte'

	const currentPath = page.url.pathname
</script>

<header class={['navbar bg-neutral text-primary fixed top-0 bottom-auto z-50']}>
	<div class="navbar-start">
		<FullscreenMenu id="fullscreen_menu" />
	</div>
	<div class="navbar-end">
		<a href="/" class="btn btn-ghost text-xl">Southern MN TCT</a>
	</div>
</header>
