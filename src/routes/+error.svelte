<script>
  import { page } from '$app/stores';

  import Fa from "svelte-fa";
  import {faWarning} from "@fortawesome/free-solid-svg-icons";
</script>

<div class="flex flex-col items-center justify-center h-full">

  <h1 class="mb-4 h1">Oops! An error occurred!</h1>
  <aside class="alert variant-ghost-error flex items-center justify-center">
    <!-- Icon -->
    <div>
      <Fa icon={faWarning} size="2x"/>
    </div>
    <!-- Message -->
    <div class="alert-message flex flex-col items-center justify-center">
      <p class="h3">Error {$page.status}</p>
      <p>{$page.error.message}</p>
    </div>
    <!-- Actions -->
    <div class="alert-actions">
      <a href="/" class="btn variant-filled">
        Go back to SafeLand
      </a>
    </div>
  </aside>
</div>