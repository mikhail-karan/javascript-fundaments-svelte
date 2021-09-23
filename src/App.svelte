<script>
  let active = 1;
</script>

<main class="flex w-full flex-col items-center mt-10 justify-center">
  <div class="btn-group">
    <button 
      on:click="{() => active = 1}"
      class="btn btn-lg {active === 1 ? 'btn-active' : ''}">
      One</button>
    <button 
      on:click="{() => active = 2}"
      class="btn btn-lg {active === 2 ? 'btn-active' : ''}">
      Two</button>
    <button
      on:click="{() => active = 3}" 
      class="btn btn-lg {active === 3 ? 'btn-active' : ''}">
      Three</button>
  </div>
</main>

<style>
</style>
