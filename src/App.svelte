<script>
  let numA = 1

  function add5(){
    numA += 5
  }

  $: multiple = numA*2


</script>

<main class="flex w-full flex-col items-center mt-10 justify-center">
  <div class="prose lg:prose-xl text-center">
    <h2 class="text-white">Conditional Rendering</h2>
    <p>This is numA: {numA}</p>
    <p>This is numA * 2: {multiple}</p>
    <div class="btn btn-primary" on:click="{add5}">Add 5 to numA</div>
    <div class="divider"></div> 
    {#if multiple > 200}
    <!-- https://daisyui.com/components/alert -->
    <div class="alert alert-error">
      <div class="flex-1">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="w-6 h-6 mx-2 stroke-current">    
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M18.364 18.364A9 9 0 005.636 5.636m12.728 12.728A9 9 0 015.636 5.636m12.728 12.728L5.636 5.636"></path>                      
        </svg> 
        <label>Those numbers are way too high!</label>
      </div>
    </div>
    {:else}
    <div class="alert alert-success">
      <div class="flex-1">
        <label>Numbers look good!</label>
      </div>
    </div>
    {/if}
  </div>
  
</main>

<style>

</style>
