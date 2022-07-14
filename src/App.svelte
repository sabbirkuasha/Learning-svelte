<script>
    import CustomComponent from './CustomComponent.svelte'
    import CustomButtons from './CustomButtons.svelte'

    let inputValue = 'Default Text'
    let inputValue2 = 'Default text2'
    let inputValue3 = 'Default Text3'
    let buttonChoosen = null
    let inputNumber = 0
    let checkStatus = null
    let favColor = null
    let favBrand = null
    let userNameInput = null

    //this means everytime inputValue varibale changes, console log the inputValue
    $:console.log(inputValue)
    $:console.log("button number is: " + buttonChoosen)
    $:console.log(1+inputNumber)
    $:console.log(checkStatus)
    $:console.log(favColor)
    $:console.log(favBrand)

    function setValue(event){
        inputValue = event.target.value
    }
    function setNumberValue(event){
        inputNumber = event.target.value
        console.log(1+inputNumber)
    }
    function saveData(){
        // console.log(document.querySelector('#userName'))
        // console.log(document.querySelector('#userName').value)
        
        console.log(userNameInput.value)
        console.dir(userNameInput)
    }

    </script>

<main>

    <!-- input and button binding together -->
    <input type="text" id="userName" 
        placeholder="Type here" 
        class="input input-bordered input-warning 
        w-full max-w-xs" 
    />
    <input type="text" id="userName" 
        bind:this={userNameInput} 
        placeholder="Type here 2" 
        class="input input-bordered input-warning 
        w-full max-w-xs" 
    />
    <button on:click={saveData}
        class="btn btn-outline btn-warning">
        Success
    </button>

    <hr class="mt-5">
    
    
    
    <!-- select input binding -->
    <h1 class="text-2xl p-5">
        Your selected Brand is {#if favBrand}
            <b class="text-blue-700">{favBrand}</b> 
            {:else} 
            <b class="text-white-700">{"empty"}</b> 
        {/if}
    </h1>
    <select bind:value={favBrand} 
    class="ml-5 select select-primary w-full max-w-xs">
        <option disabled selected>Pick your favorite Brand</option>
        <option value="Honda">Honda</option>
        <option value="Toyota">Toyota</option>
        <option value="Ferrari">Ferrari</option>
        <option value="Tesla">Tesla</option>
        <option value="Mazda">Mazda</option>
    </select>

    <hr class="mt-5">

    <!-- Radio button binding -->
    <!-- if we assign radio buttons a name then we can only choose one option -->
    <p class="flex pl-5 pt-5 text-white font-semibold">
        <input type="radio" value="red" name="colorPicker"
        bind:group={favColor} class="mr-2 checkbox checkbox-secondary" />
        Red
    </p>
    <p class="flex pl-5 pt-3 text-white font-semibold">
        <input type="radio" value="green" name="colorPicker"
        bind:group={favColor} class="mr-2 checkbox checkbox-secondary" />
        Green
    </p>
    <p class="flex pl-5 pt-3 text-white font-semibold">
        <input type="radio" value="blue" name="colorPicker"
        bind:group={favColor}  class="mr-2 checkbox checkbox-secondary" />
        Blue
    </p>
    <h1 class="text-2xl p-5">
        Your selected color is {#if favColor}
            <b class="text-{favColor}-700">{favColor}</b> 
            {:else} 
            <b class="text-white-700">{"empty"}</b> 
        {/if}
    </h1>

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
