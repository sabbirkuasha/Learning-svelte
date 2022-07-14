<script>
    export let choosenOption = null
</script>

<button class="btn " 
disabled={choosenOption==1}
on:click={()=> choosenOption=1}>Option 1</button>

<button class="btn " 
disabled={choosenOption==2}
on:click={()=> choosenOption=2}>Option 2</button>