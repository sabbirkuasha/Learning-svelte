<script>
    let inputValue = 'Default Text'
    let inputValue2 = 'Default text2'

    //this means everytime inputValue varibale changes, console log the inputValue
    $:console.log(inputValue)

    function setValue(event){
        inputValue = event.target.value
    }
</script>

<main>
   <h1 class="text-2xl font-bold p-5">Binding form </h1>
   
   <h2 class="p-5"
   >Input Value is: {inputValue}</h2>
   <input class="input input-bordered 
   input-info w-full max-w-xs ml-5"
   type="text" placeholder="Type Here"
   value={inputValue} on:input={setValue}>
   
<!-- This is shorthand in svelte -->
   <h1 class="text-2xl font-bold p-5">Binding form Approach 2</h1>
   <h2 class="p-5"
   >Input Value is: {inputValue2}</h2>
   <input class="input input-bordered 
   input-info w-full max-w-xs ml-5"
   type="text" placeholder="Type Here"
   bind:value={inputValue2}>
</main>

<style>
  
</style>
