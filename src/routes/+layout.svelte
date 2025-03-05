<script lang="ts">
	import FullscreenMenu from '$lib/components/FullscreenMenu.svelte'
	import Navbar from '$lib/components/Navbar.svelte'
	import '../app.css'
	import '@fontsource-variable/source-sans-3'
	let { children } = $props()
</script>

<FullscreenMenu />
<Navbar />

{@render children()}
