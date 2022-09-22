<script>
    import {  fly } from "svelte/transition";

    export let duration = 2000; // Slowed down animation to make it easier to see

    let innerWidth;
    
    $: flyIn={x: innerWidth, duration}; 
    $: flyOut={x: -innerWidth, duration};
 </script>
 
 <svelte:window bind:innerWidth />
 
<div class="outer-div">    
    <div in:fly={flyIn} out:fly={flyOut} class="inner-div">
        <slot/>
    </div>
</div>

 
 <style lang="scss">
    // Cleaned up the SCSS a bit since you're already using SCSS (I'm a big SCSS fan myself)
   .outer-div {
      display: grid;
      
      .inner-div {
         // Using grid and grid-area 1/1 to force the inner divs into the same area. 
         // If you don't do this you get a bouncing effect where the incoming div is
         // pushed below the outgoing div and then "pops up" jarringly.
         grid-area: 1/1;	

      }
    }
 </style>