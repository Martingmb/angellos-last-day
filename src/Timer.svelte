<script>
  import { createEventDispatcher } from "svelte";
  import { onMount, onDestroy } from "svelte";
  export let countdown = 0;
  const dispatch = createEventDispatcher();
  let timer = null;

  onMount(() => {
    timer = setInterval(() => {
      countdown -= 1;
    }, 1000);
  });

  onDestroy(() => {
    if (timer) {
      clearInterval(timer);
    }
  });

  $: {
    if (countdown === 0) {
      clearInterval(timer);
      timer = null;
      dispatch("completed");
    }
  }
</script>

<div class="container">
  <div class="centered-div">
    {countdown}
  </div>
</div>

<style>
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
  }

  .centered-div {
    width: 80%;
    height: 80%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-size: 300px;
    color: white;
  }
</style>
