<script>
  import { onMount, onDestroy } from "svelte";
  export let author;
  export let post;
  export let id;
  export let deleteItem;
  export let itemDeleted;

  let timeOnScreen = 0;

  onMount(() => {
    timeOnScreen = performance.now();
  });

  onDestroy(() => {
    const whenDestroyed = performance.now()
    console.log(`Post with Id of ${id} 'has been on screen for ${Math.ceil((whenDestroyed - timeOnScreen)/1000)}s `  )
  });
</script>

<!-- https://daisyui.com/components/card/ -->
<div class="card bg-neutral text-white w-80 shadow-xl">
  <div
    on:click={deleteItem(id)}
    class="absolute right-0 pr-2 text-error text-2xl"
  >
    x
  </div>
  <div class="card-body">
    <h2 class="card-title">{author}</h2>
    <p>{post}</p>
  </div>
</div>
