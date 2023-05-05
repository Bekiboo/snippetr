<script lang="ts">
	import { drawerStore } from '@skeletonlabs/skeleton'

	function drawerClose(): void {
		drawerStore.close()
	}
</script>

<nav
	class="list-nav p-4 h-full bg-gray-900 bg-clip-padding backdrop-filter backdrop-blur-sm bg-opacity-20"
>
	<ul>
		<li><a href="/" on:click={drawerClose}>Homepage</a></li>
		<li><a href="/about" on:click={drawerClose}>About</a></li>
		<li><a href="/blog" on:click={drawerClose}>Blog</a></li>
		<li><a href="/contact" on:click={drawerClose}>Contact</a></li>
	</ul>
</nav>
