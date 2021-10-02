<script>
  
  import data from "./data.json";
  import Post from "./components/Post.svelte"
  import AddForm from "./components/AddForm.svelte"
  import Nav from "./components/Nav.svelte"
  import { Router, Route } from "svelte-navigator";

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

<Router>
  <main class="flex w-full flex-col items-center mt-10 justify-center space-y-5">
    <Nav />
    <Route>
      <AddForm addPost={addPost} />
    </Route>
    <Route path="posts">
      <h1>Posts</h1>
      {#each posts.reverse() as post}
        <Post deletePost={deletePost} id={post.id} author={post.author} post={post.post} />
      {/each}
    </Route>
  </main>
</Router>

<style>
</style>
