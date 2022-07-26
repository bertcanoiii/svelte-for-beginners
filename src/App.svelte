<script>
    import data from "./data.json";

    let posts = data.data;
    let author = '';
    let post = '';

    function submitForm() {
        const newPost = {
            id: posts.length +1,
            author: author,
            date_created: '07/26/2022',
            post: post
        }

        posts.push(newPost)
        posts = posts

        author = ''
        post = ''

    }
</script>

<main>
    <div class="flex flex-col justify-center items-center bg-slate-500 p-10 rounded-3xl space-y-6">

        <div class="form-control w-80 items-center">
            <label for="author" class="label font-bold text-2xl">Author</label>
            <input bind:value={author} id="author" name="author" type="text" placeholder="Author"
                   class="input input-bordered w-full max-w-xs"/>
            <label for="post" class="label">
                <span class="label font-bold text-m">Your Post</span>
            </label>
            <textarea bind:value={post} id="post" class="textarea textarea-bordered h-24 w-full"
                      placeholder="Post"></textarea>
            <button on:click={submitForm} class="btn mt-6">Submit</button>
        </div>

            <div class="overflow space-y-2 ">
                {#each posts.reverse() as post}
                <div class="card w-96 bg-base-100 shadow-xl">
                    <div class="card-body items-start">
                        <h2 class="card-title">{post.author}</h2>
                        <p>Date: {post.date_created}</p>
                        <p>{post.post}</p>
                    </div>
                </div>
                {/each}
            </div>

    </div>
</main>

<style>
</style>
