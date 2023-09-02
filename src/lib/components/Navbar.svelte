<script lang="ts">
  import { getDrawerStore } from "@skeletonlabs/skeleton";
  import Fa from "svelte-fa";

  const drawerStore = getDrawerStore();

  // Used to close the drawer when changing the path
  function drawerClose(): void {
    drawerStore.close();
  }

  import {faX} from "@fortawesome/free-solid-svg-icons";
</script>

<!-- This navigation component contains the sidebar links -->
<nav class="list-nav p-4">
  <div class="flex items-center justify-content">
    <h2 class="p-4">Navigation</h2>
    <span class="" on:click={drawerClose}>
			<button type="button" class="btn-icon variant-ghost">
        <Fa icon={faX} />
			</button>
		</span>
  </div>

  <hr class="p-1"/>
  <ul>
    <li><a href="/" on:click={drawerClose}>Home</a></li>
    <li><a href="/projects" on:click={drawerClose}>Projects</a></li>
    <li><a href="/about" on:click={drawerClose}>About me</a></li>
    <li><a href="/contact" on:click={drawerClose}>Contact</a></li>
  </ul>
</nav>