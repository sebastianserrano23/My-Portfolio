<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-rocket.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { AppShell, AppBar, LightSwitch, Drawer, drawerStore, popup, storePopup } from '@skeletonlabs/skeleton';
	import type { PopupSettings } from '@skeletonlabs/skeleton';
	import { computePosition, autoUpdate, offset, shift, flip, arrow } from '@floating-ui/dom';
	storePopup.set({ computePosition, autoUpdate, offset, shift, flip, arrow });
	function openSideBar(): void {
		drawerStore.open();
	}
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			<svelte:fragment slot="lead"><LightSwitch /></svelte:fragment>
				<strong class="text-xl uppercase">The Brogrammer</strong>
			<svelte:fragment slot="trail">
				<button class="btn variant-filled">
					Home
				</button>
				<button class="btn variant-filled">
					<a href="https://www.linkedin.com/in/sebastian-serrano-a11a57198?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BasHmyvdlQW%2BJYuuByYcy4A%3D%3D"
						target="_blank"
						rel="noreferrer">
						LinkedIn
					</a>
				</button>
				<button class="btn variant-filled">
					<a href="https://github.com/sebastianserrano23/"
						target="_blank"
						rel="noreferrer">
						GitHub
					</a>
				</button>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
