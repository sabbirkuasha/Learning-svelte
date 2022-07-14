<script>
    import CustomComponent from './CustomComponent.svelte'
    import CustomButtons from './CustomButtons.svelte'

    let inputValue = 'Default Text'
    let inputValue2 = 'Default text2'
    let inputValue3 = 'Default Text3'
    let buttonChoosen = null
    let inputNumber = 0
    let checkStatus = null
    
    //this means everytime inputValue varibale changes, console log the inputValue
    $:console.log(inputValue)
    $:console.log("button number is: " + buttonChoosen)
    $:console.log(1+inputNumber)
    $:console.log(checkStatus)

    function setValue(event){
        inputValue = event.target.value
    }
    function setNumberValue(event){
        inputNumber = event.target.value
        console.log(1+inputNumber)
    }

</script>

<main>

    <!-- checkbox binding -->
    <p class="flex p-5 text-white font-semibold">
        <input type="checkbox" bind:checked= {checkStatus}
        class="mr-2 checkbox checkbox-primary" />
        I accept the Terms and conditions
    </p>
    


    <!-- input number -->
    <h1 class="text-2xl font-bold pl-5 mt-5">
        Input number  
    </h1>
   <input type="number" class="input input-bordered input-success
   w-full max-w-xs ml-5" 
   bind:value={inputNumber}
   >
   
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
