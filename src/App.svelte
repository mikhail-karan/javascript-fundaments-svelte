<script>
  import data from "./data.json";
  import Post from "./components/Post.svelte"
  import AddForm from "./components/AddForm.svelte"

  let posts = data.data;

  let arrayInc = posts.length

  function addPost(author, post) {
    
    const postObj = {
      author: author,
      post: post,
      id: ++arrayInc,
    };

    posts.push(postObj);
    posts = posts;
  }

  function deletePost(id){
    const deleteIndex = posts.findIndex(post => post.id === id)
    posts.splice(deleteIndex, 1)
    posts = posts;
  }
</script>

<main class="flex w-full flex-col items-center mt-10 justify-center space-y-5">
  <AddForm addPost={addPost} />
  {#each posts.reverse() as post}
    <Post deleteItem={deletePost} author={post.author} post={post.post} id={post.id} />
  {/each}
</main>

<style>
</style>
