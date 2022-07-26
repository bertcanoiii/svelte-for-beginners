<script>
    import data from "./data.json"

    let posts = data.data
</script>

<main>
 <div  class="flex flex-col justify-center items-center space-y-6">
     {#each posts as post}
         <div class="card w-96 bg-base-100 shadow-xl">
             <div class="card-body items-start">
                 <h2 class="card-title">{post.author}</h2>
                 <p>Date: {post.date_created}</p>
                 <p>{post.post}</p>
             </div>
         </div>
     {/each}
 </div>
</main>

<style>
</style>
