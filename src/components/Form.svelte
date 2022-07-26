<script>
    export let submitForm;
    let author = '';
    let post = '';

    function sendSubmitForm(){
        submitForm(author, post);
        author = '';
        post = '';
    }
</script>

<h1 class="font-bold">Add Post</h1>
<div class="form-control w-80 items-center">
    <label for="author" class="label font-bold text-2xl">Author</label>
    <input bind:value={author} id="author" name="author" type="text" placeholder="Author"
           class="input input-bordered w-full max-w-xs"/>
    <label for="post" class="label">
        <span class="label font-bold text-m">Your Post</span>
    </label>
    <textarea bind:value={post} id="post" class="textarea textarea-bordered h-24 w-full"
              placeholder="Post"></textarea>
    <button on:click={sendSubmitForm} class="btn bert-btn mt-6">Submit</button>
</div>