<script>
  import { onMount, onDestroy, beforeUpdate, tick } from "svelte";
  export let author;
  export let post;
  export let id;
  export let deleteItem;

  let timeOnScreen = 0;
  let timeInterval = null;

  beforeUpdate(async () => {
  	console.log('the component is about to update');
  	await tick();
  	console.log('the component just updated');
  });

  onMount(() => {
    console.log("Post Created");
    timeInterval = setInterval(() => {
      ++timeOnScreen;
      console.log(`Interval updated for post id ${id}`)
    },1000);
    // initDestroy(id, author)
  });

  onDestroy(() => {
    clearInterval(timeInterval);
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
    <h2 class="card-title">{author} {timeOnScreen}</h2>
    <p>{post}</p>
  </div>
</div>
