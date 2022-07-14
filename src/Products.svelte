<script>
    import {createEventDispatcher} from 'svelte'

    let dispatch = createEventDispatcher()

    export let price = '1200'
    export let ProductName
    export let id = '0'
    export let badge = null

    

function addtocart(){
    dispatch('add-to-cart-btn', 
        {
            id : id,
            ProductName: ProductName,
            price: price,
            badge: badge
        })
}
function deletebtn(){
    dispatch('delete-btn',
        {
            id : id,
            ProductName: ProductName,
            price: price,
            badge: badge
        })
}
</script>

<main>
    <article>
        <div class="p-6">
            {#if badge}
                <div class="badge badge-secondary badge-outline">
                    {badge}
                </div>    
            {/if}
            

            <h1 class="pb-2 text-3xl">
                {id}: {ProductName}
            </h1>
            
            <h2 class="pb-2 text-2xl">
                Price: {price}
            </h2>
            
            <button on:click = {addtocart}
            class="mr-3 btn btn-primary">
                Add to cart
            </button>
            <button on:click = {deletebtn}
            class="btn btn-error">
                Delete
            </button>
        </div>
        
    </article>
</main>