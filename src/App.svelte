<script>
  import Counter from "./lib/Counter.svelte";
  import Modal from "./Modal.svelte";

import Products from "./Products.svelte";

let agreeTerm = false

  let allProducts = [
    {
      id: '0',
      ProductName: 'Proneeti',
      price: '14900'
    },
    {
      id: '1',
      ProductName: 'Ruchika',
      price: '14000',
      badge: "New Arrival"
    },
    {
      id: '2',
      ProductName: 'Aarabhi',
      price: '13000'
    },
    {
      id: '3',
      ProductName: 'Aadriya',
      price: '14300',
      badge: "Best Seller"
    },

  ]

  function addtocart(event){
    console.log(event.detail)
  }
  function deletebtn(event){
    console.log(event.detail)
  }
</script>

<main>
  <Modal>
    <h1 slot="Headline" 
    class="text-4xl font-bold">
      This is Headline of modal comp 1
    </h1>
    <h1 
    class="text-xl font-bold">
      This is also in modal comp 1
    </h1>
    <p class="bg-teal-200 text-black font-bold">
      This also works, this is first one
    </p>


    <div class="flex flex-row mt-6 items-center">
      <div class="">
        
          <label 
          class="label cursor-pointer align-middle">
            <input type="checkbox" class="toggle toggle-primary" bind:checked={agreeTerm} />
          </label>
        
      </div>
      <div class="alert alert-info shadow-lg">
        <div>
          {#if agreeTerm === true}
            <svg xmlns="http://www.w3.org/2000/svg" class="stroke-current flex-shrink-0 h-6 w-6" fill="none" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
          {:else}
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="stroke-current flex-shrink-0 w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
          {/if}
          <span>I agree with the terms & conditions</span>
        </div>
      </div>
    </div>

    <svelte:fragment slot="footer">
      {#if agreeTerm === true}
      <label for="my-modal" class="btn">
        Now you can Close it
      </label>
      {/if}
    </svelte:fragment>

  </Modal>
  
  
  {#each allProducts as product}
  <Products
  
  {...product}
  on:add-to-cart-btn = {addtocart}
  on:delete-btn = {deletebtn}
  />    
  {/each}

  
</main>

<style>
  
</style>
