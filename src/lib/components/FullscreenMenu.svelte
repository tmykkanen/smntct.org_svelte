<script lang="ts">
	import Icon from '@iconify/svelte'
	import navData from '$lib/assets/navData.js'
	import { onMount } from 'svelte'

	interface Props {
		id: string
	}

	const { id }: Props = $props()
	// Make typescript happy
	let idHTML: HTMLDialogElement
	onMount(() => {
		idHTML = document.getElementById(id) as HTMLDialogElement
	})
</script>

<button onclick={() => idHTML.showModal()} class="btn btn-square btn-ghost">
	<Icon icon="ci:hamburger-lg" class="text-2xl" />
</button>

<dialog {id} class="modal">
	<div
		class="text-primary modal-box bg-neutral size-full max-h-screen max-w-screen rounded-none px-8 py-0"
	>
		<!-- Menu Heading -->
		<div class="flex items-center justify-between border-b border-b-neutral-200 py-3">
			<h3 class="text-primary my-0 text-lg font-bold">
				<a href="/" class="btn btn-ghost text-2xl" onclick={() => idHTML.close()}>
					Southern MN TCT</a
				>
			</h3>
			<!-- Close btn -->
			<form method="dialog">
				<button class="btn btn-sm btn-circle btn-ghost">
					<Icon icon="material-symbols:close-rounded" class="text-2xl" />
				</button>
			</form>
		</div>

		<!-- Menu Body -->
		<div class="overflow-y-auto">
			<ul class="menu px-0">
				{#each navData as { path, name, submenu }}
					<li class="px-0">
						<a
							href={path}
							class="btn btn-ghost justify-start text-2xl font-normal"
							onclick={() => idHTML.close()}>{name}</a
						>
						{#if submenu}
							<ul class="menu my-0">
								{#each submenu as { name, path }}
									<li>
										<a
											href={path}
											class="btn btn-ghost justify-start text-xl font-normal"
											onclick={() => idHTML.close()}>{name}</a
										>
									</li>
								{/each}
							</ul>
						{/if}
					</li>
				{/each}
			</ul>
		</div>
	</div>
</dialog>
