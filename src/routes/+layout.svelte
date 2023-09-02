<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppBar, LightSwitch, Drawer, initializeStores } from "@skeletonlabs/skeleton";

	// Highlight JS
	import hljs from 'highlight.js';
	import 'highlight.js/styles/github-dark.css';
	import { storeHighlightJs } from '@skeletonlabs/skeleton';
	storeHighlightJs.set(hljs);

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });

	// FontAwesome Icons
	import Fa from "svelte-fa";
	import {faLinkedinIn} from "@fortawesome/free-brands-svg-icons";
	import {faEnvelope} from "@fortawesome/free-solid-svg-icons";
	import {faBars} from "@fortawesome/free-solid-svg-icons";

	// Popup for the navbar
	// import { popup } from '@skeletonlabs/skeleton';
	// import type { PopupSettings } from '@skeletonlabs/skeleton';

	import Navbar from "../lib/components/Navbar.svelte";

	// Drawer init
	import { getDrawerStore } from "@skeletonlabs/skeleton";
	initializeStores();
	const drawerStore = getDrawerStore();

	function drawerOpen() {
		drawerStore.open({width: "w-50%"});
	}
</script>

<!-- Navbar Drawer -->
<Drawer >
	<Navbar />
</Drawer>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<div on:click={drawerOpen}>
					<Fa icon={faBars} class="m-2" />
				</div>
				<strong class="text-xl uppercase">
					<a href="/">CrouzyCorp</a>
				</strong>

			</svelte:fragment>
			<svelte:fragment slot="trail">
				<LightSwitch />
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://linkedin.com/in/maxencecrouzy"
					target="_blank"
					rel="noreferrer"
				>
					<Fa icon={faLinkedinIn} size="2x" />
				</a>
				<!-- TODO: Insert CrouzyCorp mail here -->
				<a
					class="btn btn-sm variant-ghost-surface"
					href="mailto:tt@test.com"
					target="_blank"
					rel="noreferrer"
				>
					<Fa icon={faEnvelope} size="2x" />
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
