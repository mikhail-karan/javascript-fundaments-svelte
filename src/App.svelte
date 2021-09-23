<script>
  import data from './data.json'

  let posts = data.data


</script>

<main class="flex w-full flex-col items-center mt-10 justify-center space-y-5">
  <!-- https://daisyui.com/components/card/ -->
  <!-- mention we are declaring post as a new variable that can be any name. It is not auto generated -->
  {#each posts as post }
    <div class="card bg-neutral text-white w-80 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">{post.author}</h2> 
        <!-- Parent and child can have the same name -->
        <p>{post.post}</p> 
      </div>
    </div>
  {/each}

</main>

<style>
</style>
