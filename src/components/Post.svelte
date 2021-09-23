<script>
 export let author;
 export let post;
</script>
<!-- https://daisyui.com/components/card/ -->
<div class="card bg-neutral text-white w-80 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">{author}</h2>
    <p>{post}</p>
  </div>
</div>