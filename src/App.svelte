<script>
  import Timer from "./Timer.svelte";
  import Last from "./Last.svelte";
  let done = false;
</script>

{#if done}
  <Last />
{:else}
  <Timer countdown={10} on:completed={() => (done = true)} />
{/if}

<style>
  :global(body) {
    background-color: rgb(42, 41, 41);
  }
</style>
