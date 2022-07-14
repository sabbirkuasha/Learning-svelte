<script>
    import CustomComponent from './CustomComponent.svelte'
    import CustomButtons from './CustomButtons.svelte'

    let inputValue = 'Default Text'
    let inputValue2 = 'Default text2'
    let inputValue3 = 'Default Text3'
    let buttonChoosen = null
    
    //this means everytime inputValue varibale changes, console log the inputValue
    $:console.log(inputValue)
    $:console.log("button number is: " + buttonChoosen)

    function setValue(event){
        inputValue = event.target.value
    }

</script>

<main>
   <h1 class="text-2xl font-bold pl-5 mt-5">Binding form </h1>
   
   <h2 class="pl-5"
   >Input Value is: {inputValue}</h2>
   <input class="input input-bordered 
   input-info w-full max-w-xs ml-5"
   type="text" placeholder="Type Here"
   value={inputValue} on:input={setValue}>
   
<!-- This is shorthand in svelte -->
   <h1 class="text-2xl font-bold pl-5 mt-5">Binding form Approach 2</h1>
   <h2 class="pl-5"
   >Input Value is: {inputValue2}</h2>
   <input class="input input-bordered 
   input-info w-full max-w-xs ml-5"
   type="text" placeholder="Type Here"
   bind:value={inputValue2}>

   <!-- This is CustomComponent Binding -->
   <h1 class="text-2xl font-bold mt-5 pl-5">Binding form Custom Component</h1>
   <h2 class="pl-5"
   >Input Value is: {inputValue3}</h2>
   <!-- This will only works for dynamic value, not dynamic type -->
   <CustomComponent bind:inputValue3={inputValue3}/>

   <!-- this is custom buttons -->
   <CustomButtons bind:choosenOption={buttonChoosen}/>


</main>

<style>
  
</style>
