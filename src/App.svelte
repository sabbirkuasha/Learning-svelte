<script>
    let inputValue = 'Default Text'


    function setValue(event){
        inputValue = event.target.value
    }
</script>

<main>
   <h1>Binding form </h1>

   <h2 class="p-5"
   >Input Value is: {inputValue}</h2>
   <input class="input input-bordered 
   input-info w-full max-w-xs ml-5"
   type="text" placeholder="Type Here"
   value={inputValue} on:input={setValue}>
</main>

<style>
  
</style>
