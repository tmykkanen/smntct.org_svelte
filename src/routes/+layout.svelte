<script lang="ts">
	import Navbar from '$lib/components/Navbar.svelte'
	import '../app.css'
	import '@fontsource-variable/source-sans-3'
	let { children } = $props()
</script>

<Navbar />

{@render children()}
