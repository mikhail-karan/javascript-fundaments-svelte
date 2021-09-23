<script>
  import data from "./data.json";

  let posts = data.data;
  let name = "";
  let postText = "";

  // Example for how data binding works 
  // console.log(name)
  // $: testName = console.log(name)

  // Explain that adding a post does not write to file
  function addPost() {
    const post = {
      author: name,
      post: postText,
      id: posts.length + 1,
    };

    posts.push(post);
    posts = posts;
    name = "";
    postText = "";
  }
</script>

<main class="flex w-full flex-col items-center mt-10 justify-center space-y-5">
  <h2>Add Post</h2>
  <div class="form-control">
    <label for="id" class="label">
      <span class="label-text">Name</span>
    </label>
    <!-- Explain binding -->
    <!-- Connecting/binding the value of input box to the variable name -->
    <input
      type="text"
      bind:value={name}
      placeholder="Enter Name"
      class="input input-bordered"
    />
    <label for="id" class="label">
      <span class="label-text">Post</span>
    </label>
    <textarea
      class="textarea h-24 textarea-bordered"
      bind:value={postText}
      placeholder="Enter Post"
    />
    <button on:click={addPost} class="btn btn-primary mt-5">Submit</button>
  </div>
  <!-- https://daisyui.com/components/card/ -->
  {#each posts.reverse() as post}
    <div class="card bg-neutral text-white w-80 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">{post.author}</h2>
        <p>{post.post}</p>
      </div>
    </div>
  {/each}
</main>

<style>
</style>
