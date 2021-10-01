<script>
  
  import data from "./data.json";
  import Post from "./components/Post.svelte"
  import AddForm from "./components/AddForm.svelte"
  import Alert from "./components/Alert.svelte"

  let posts = data.data;

  let alertActive = false

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

  function postDeleted(){
    alertActive = true
    setTimeout(() => alertActive = false ,2000)
  }
</script>

<main class="flex w-full flex-col items-center mt-10 justify-center space-y-5">
  {#if alertActive}
  <Alert  />
  {/if}
  <AddForm addPost={addPost} />
  {#each posts.reverse() as post}
    <Post itemDeleted={postDeleted} deleteItem={deletePost} author={post.author} post={post.post} id={post.id} />
  {/each}
</main>

<style>
</style>
