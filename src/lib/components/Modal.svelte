<script lang="ts">
	// https://zachpatrick.com/blog/build-a-modal-component-with-svelte

	import { fade, fly } from 'svelte/transition'
	import { trapFocus } from '$lib/code/trapFocus.js'

	// Trap all keyboard navigation inside the modal
	function initTrapFocus(e: KeyboardEvent) {
		return trapFocus(e, 'modal')
	}

	// Close the modal when the escape button is pressed
	function closeWithEscape(e: KeyboardEvent) {
		if (e.key === 'Escape') {
			isOpen = false
		}
	}

	export let isOpen = false
</script>

<!-- Addd keyboard event listeners to window while modal is open -->
<svelte:window onkeydown={initTrapFocus} onkeyup={closeWithEscape} />

<div
	role="dialog"
	id="modal"
	class="fixed inset-0 z-50 flex items-start justify-center overflow-auto overscroll-contain"
	class:window-noscroll={isOpen}
>
	<div
		id="modal-overlay"
		class="fixed inset-0 z-10 bg-black/50"
		aria-hidden="true"
		onclick={() => (isOpen = false)}
		transition:fade={{ duration: 100 }}
	></div>
	<div class="relative z-20 mx-auto my-auto" transition:fly={{ y: -60, duration: 250 }}>
		<p class="text-accent">Modal content goes here</p>
	</div>
</div>

<style>
	:global(html:has(.window-noscroll), html:has(.window-noscroll) body) {
		overflow: hidden;
	}

	:global(header.site-header),
	:global(#main) {
		transition: filter 500ms;
	}

	:global(html:has(.window-noscroll) header.site-header),
	:global(html:has(.window-noscroll) #main) {
		filter: blur(5px);
	}
</style>
