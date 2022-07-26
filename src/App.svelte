<script>
    import {Router, Route, navigate} from 'svelte-navigator';
    import data from "./data.json";
    import Post from "./components/Post.svelte";
    import Form from "./components/Form.svelte";
    import NavBar from "./components/NavBar.svelte";

    let posts = data.data;

    function submitForm(author, post) {
        const newPost = {
            id: posts.length +1,
            author: author,
            post: post
        }
        posts.push(newPost)
        posts = posts
        navigate('/posts')
    }
</script>

<Router>
    <main class="">
        <div class="flex flex-col justify-center items-center bg-slate-500 p-10 rounded-3xl">
            <NavBar></NavBar>
            <Route>
                <Form submitForm={submitForm}/>
            </Route>
            <Route path="posts">
                <div class="overflow-auto space-y-2 ">
                    {#each posts.reverse() as post}
                     <Post {...post}></Post>
                    {/each}
                </div>
            </Route>
        </div>
    </main>
</Router>

<style>
</style>
