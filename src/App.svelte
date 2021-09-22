<script>
  let active = 0;
</script>

<main class="flex w-full flex-col items-center mt-10 justify-center">
  <div class="btn-group">
    <button 
      on:click="{() => active = 0}"
      class="btn btn-lg {active === 0 ? 'btn-active' : ''}">
      Large
    </button>
    <button 
      on:click="{() => active = 1}"
      class="btn btn-lg {active === 1 ? 'btn-active' : ''}">
      Large</button>
    <button
      on:click="{() => active = 2}" 
      class="btn btn-lg {active === 2 ? 'btn-active' : ''}">
    Large</button>
  </div>
</main>

<style>
</style>
