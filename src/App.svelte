<script>
    let number = 1;

    function addFive(){
        number += 5;
    }

    $: double = number*2
</script>

<main class="flex flex-col justify-center items-center">
    <p>The number is: {number}</p>
    <button class="btn" on:click={addFive}>
        Add 5
    </button>
    <p>The number divided by 2 is {double}</p>

    {#if double < 50}
    <div class="alert alert-success shadow-lg">
        <div>
            <svg xmlns="http://www.w3.org/2000/svg" class="stroke-current flex-shrink-0 h-6 w-6" fill="none" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
            <span>Number is good!</span>
        </div>
    </div>
    {:else if double > 50 && double < 100}
    <div class="alert alert-warning shadow-lg">
        <div>
            <svg xmlns="http://www.w3.org/2000/svg" class="stroke-current flex-shrink-0 h-6 w-6" fill="none" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z" /></svg>
            <span>Warning: Number higher than 50!</span>
        </div>
    </div>
    {:else}
    <div class="alert alert-error shadow-lg">
        <div>
            <svg xmlns="http://www.w3.org/2000/svg" class="stroke-current flex-shrink-0 h-6 w-6" fill="none" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
            <span>Error! NUMBER HIGHER THAN 100.</span>
        </div>
    </div>
    {/if}

</main>

<style>
</style>
