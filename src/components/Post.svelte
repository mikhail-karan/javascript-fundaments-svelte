<script>
  import {onMount} from 'svelte'
  export let author;
  export let post;
  export let id;
  export let deleteItem;

  onMount(() => {
    console.log(author, ' post mounted')

    return () => console.log('post unmounted')
  })
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
