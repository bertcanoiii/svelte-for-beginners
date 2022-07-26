<script>
    import {Link, useLocation} from 'svelte-navigator';
    const location = useLocation();
</script>

<div class="flex space-x-4 mb-5">
    <Link to="/" class="link link-hover text-white text-xl font-bold {$location.pathname === '/' ? 'underline' : ''}">Add post</Link>
    <Link to="/posts" class="link link-hover text-white text-xl font-bold  {$location.pathname === '/posts' ? 'underline' : ''}">Posts</Link>
</div>