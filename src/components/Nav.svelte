<script>
  import { Link, useLocation } from "svelte-navigator";
  const location = useLocation();

  $: console.log($location.pathname);
</script>

<div class="flex space-x-4">
  <Link to="/"><span class="text-primary {$location.pathname === '/' ? 'underline text-secondary' : ''}">Add Post</span></Link>
  <Link to="/posts"><span class="text-primary {$location.pathname === '/posts' ? 'underline text-secondary' : ''}">Posts</span></Link>
</div>
