<script lang="ts">
	// The ordering of these imports is critical to your app working properly (theme, styles, app.postcss)
	import '@skeletonlabs/skeleton/themes/theme-crimson.css'
	import '@skeletonlabs/skeleton/styles/all.css'
	import '../app.postcss'

	import { page } from '$app/stores'

	import { AppBar, AppShell } from '@skeletonlabs/skeleton'
	import { Drawer, drawerStore } from '@skeletonlabs/skeleton'
	import Navigation from './components/Navigation.svelte'

	function drawerOpen(): void {
		drawerStore.open({})
	}
</script>

<Drawer background="bg-secondary-500 md:bg-primary-500">
	<h2 class="p-4">Navigation</h2>
	<hr />
	<Navigation />
</Drawer>

<AppShell slotSidebarLeft="bg-surface-500/5 w-0 lg:w-64">
	<svelte:fragment slot="header">
		<AppBar background="bg-primary-500 opacity-90" fixed="top" sticky="top" shadow="shadow-xl">
			<svelte:fragment slot="lead">
				<div class="flex items-center">
					<button class="lg:hidden btn btn-sm mr-4" on:click={drawerOpen}>
						<span>
							<svg viewBox="0 0 100 80" class="fill-token w-4 h-4">
								<rect width="100" height="20" />
								<rect y="30" width="100" height="20" />
								<rect y="60" width="100" height="20" />
							</svg>
						</span>
					</button>
					<strong class="text-xl uppercase">Skeleton</strong>
				</div>
			</svelte:fragment></AppBar
		>
	</svelte:fragment>

	<svelte:fragment slot="sidebarLeft">
		<Navigation />
	</svelte:fragment>

	<!-- Page Content -->
	<slot />
</AppShell>
