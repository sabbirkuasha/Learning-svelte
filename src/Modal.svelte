<script>
    
</script>


<label  for="my-modal" 
        class="btn modal-button">
    open modal
</label>


<input  type="checkbox" 
        id="my-modal" 
        class="modal-toggle" 
/>
<div class="modal">
    <div class="modal-box">
        <h3 class="font-bold text-lg border-b-2">
            <slot   name="Headline" 
                    class="border"/>
        </h3>
        <p class="py-4">
            <slot/>
        </p>
        <div class="modal-action">
            <slot name="footer">
                <label for="my-modal" class="btn" disabled>
                    Agree with the terms & coonditions
                </label>
            </slot>
            
        </div>
    </div>
</div>