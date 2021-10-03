<script>
  import Post from "./components/Post.svelte";
  import AddForm from "./components/AddForm.svelte";
  import Nav from "./components/Nav.svelte";
  import { Router, Route } from "svelte-navigator";
  import { storedPosts } from "./stores";
</script>

<Router>
  <main
    class="flex w-full flex-col items-center mt-10 justify-center space-y-5"
  >
    <Nav />
    <Route>
      <AddForm />
    </Route>
    <Route path="posts">
      <h1>Posts</h1>
      {#each $storedPosts.reverse() as post}
        <Post id={post.id} author={post.author} post={post.post} />
      {/each}
    </Route>
  </main>
</Router>

<style>
</style>
