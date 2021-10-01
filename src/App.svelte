<script>
  
  import data from "./data.json";
  import Post from "./components/Post.svelte"
  import AddForm from "./components/AddForm.svelte"
  import Alert from "./components/Alert.svelte"
  import { Router, Route, Link } from "svelte-navigator";

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
</script>

<Router>
  <main class="flex w-full flex-col items-center mt-10 justify-center space-y-5">
    <div class="flex space-x-4">
      <Link to="/">Add Post</Link>
      <Link to="/posts">Posts</Link>
    </div>
    <Route>
      <AddForm addPost={addPost} />
    </Route>
    <Route path="posts">
      {#each posts.reverse() as post}
        <Post deleteItem={deletePost} author={post.author} post={post.post} id={post.id} />
      {/each}
    </Route>
  </main>
</Router>

<style>
</style>
