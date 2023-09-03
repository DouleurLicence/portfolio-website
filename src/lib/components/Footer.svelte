<script lang="ts">

  import Fa from "svelte-fa";

  import {faCopyright} from "@fortawesome/free-solid-svg-icons";

  const currentYear = new Date().getFullYear();
</script>

<div class="card flex items-center justify-center">
  <footer class="m-2">
    <p class="text-center">Developed by CrouzyCorp©, {currentYear} - with ♥ and <a href="https://kit.svelte.dev" class="anchor">SvelteKit</a></p>
  </footer>
</div>