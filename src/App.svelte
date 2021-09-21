<script>
  let numA = 1

  function add5(){
    numA += 5
  }

  $: multiple = numA*2


</script>

<main class="flex w-full flex-col items-center mt-10 justify-center">
  <div class="prose lg:prose-xl text-center">
    <h2 class="text-white">Lets get Reactive</h2>
    <p>This is numA: {numA}</p>
    <p>This is numA * 2: {multiple}</p>
    <div class="btn btn-primary" on:click="{add5}">Add 5 to numA</div>
  </div>
</main>

<style>

</style>
