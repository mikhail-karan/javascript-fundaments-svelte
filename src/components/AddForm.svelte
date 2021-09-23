<script>
  export let addPost;
  let author;
  let post;

  function submitForm() {
    addPost(author, post);
    author = "";
    post = "";
  }
</script>

<h2>Add Post</h2>
<div class="form-control">
  <label for="id" class="label">
    <span class="label-text">Name</span>
  </label>
  <input
    type="text"
    bind:value={author}
    placeholder="Enter Name"
    class="input input-bordered"
  />
  <label for="id" class="label">
    <span class="label-text">Post</span>
  </label>
  <textarea
    class="textarea h-24 textarea-bordered"
    bind:value={post}
    placeholder="Enter Post"
  />
  <button on:click={submitForm} class="btn btn-primary mt-5"
    >Submit</button
  >
</div>
