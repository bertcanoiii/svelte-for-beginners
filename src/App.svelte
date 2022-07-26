<script>
    import data from "./data.json";
    import Post from "./components/Post.svelte";
    import Form from "./components/Form.svelte";

    let posts = data.data;

    function submitForm(author, post) {
        const newPost = {
            id: posts.length +1,
            author: author,
            post: post
        }

        posts.push(newPost)
        posts = posts

    }
</script>

<main>
    <div class="flex flex-col justify-center items-center bg-slate-500 p-10 rounded-3xl space-y-6">

        <Form submitForm={submitForm}/>

        <div class="overflow space-y-2 ">
            {#each posts.reverse() as post}
             <Post {...post}></Post>
            {/each}
        </div>
    </div>
</main>

<style>
</style>
