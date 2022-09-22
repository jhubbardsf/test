<script>
   import { swipe } from "svelte-gestures";
   import { slide, fade, fly } from "svelte/transition";
   let navigation = "szendvics";

   let innerWidth;
   const duration = 2000; // Slowed down animation to make it easier to see
   $: flyIn={x: innerWidth, duration}; // Needed to be reactive because x is undefined on first render
   // Above is equivalent to below, same shortcut as the binding when using the same variable name
   // $: flyIn={x: innerWidth, duration: duration};

   $: flyOut={x: -innerWidth, duration};  // Needed to be reactive because x is undefined on first render
   $: console.log({innerWidth}); // Look at the console to see innerWidth being undefined initially then changing to the correct value
</script>

<!-- Binds the innerWidth variable to the width of the monitor to give a more fluid motion -->
<svelte:window bind:innerWidth />
<!-- Above is equivalent to below, shortcut for binding when you make them the same name -->
<!-- <svelte:window bind:innerWidth={innerWidth} /> -->

<main>

   <div class="nav">
      <div class="szendvics" on:click={() => {navigation = "szendvics"}}><p class:active="{navigation == "szendvics"}">szendvics</p></div>
      <div class="ital" on:click={() => {navigation = "ital"}}><p class:active="{navigation == "ital"}">ital</p></div>
      <div class="pogi" on:click={() => {navigation = "pogi"}}><p class:active="{navigation == "pogi"}">pogi</p></div>
   </div>

   <div class="outer-div">
      {#if navigation == "szendvics"}
         <div in:fly={flyIn} out:fly={flyOut} class="inner-div">
            <div class="grid-container">
               <div class="grid-cell-icon"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text">szenya</div>
               <div class="grid-cell-price">69420Ft</div>
               <div class="grid-cell-icon lite"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text lite">Szaros szendvics</div>
               <div class="grid-cell-price lite">69420Ft</div>
               <div class="grid-cell-icon"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text">Marhahúsos szendvics</div>
               <div class="grid-cell-price">69420Ft</div>
               <div class="grid-cell-icon lite"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text lite">Szaros szendvics</div>
               <div class="grid-cell-price lite">69420Ft</div>
               <div class="grid-cell-icon"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text">Marhahúsos szendvics</div>
               <div class="grid-cell-price">69420Ft</div>
               <div class="grid-cell-icon lite"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text lite">Szaros szendvics</div>
               <div class="grid-cell-price lite">69420Ft</div>
               <div class="grid-cell-icon"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text">Marhahúsos szendvics</div>
               <div class="grid-cell-price">69420Ft</div>
               <div class="grid-cell-icon lite"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text lite">Szaros szendvics</div>
               <div class="grid-cell-price lite">69420Ft</div>
               <div class="grid-cell-icon"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text">Marhahúsos szendvics</div>
               <div class="grid-cell-price">69420Ft</div>
               <div class="grid-cell-icon last lite"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text last lite">Rántotthúsos szendvics</div>
               <div class="grid-cell-price last lite">69420Ft</div>
            </div>
         </div>
      {/if}
      {#if navigation == "ital"}
         <div in:fly={flyIn} out:fly={flyOut} class="inner-div">
            <div class="grid-container">
               <div class="grid-cell-icon"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text">hell</div>
               <div class="grid-cell-price">69420Ft</div>
               <div class="grid-cell-icon lite"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text lite">szikszo</div>
               <div class="grid-cell-price lite">69420Ft</div>
               <div class="grid-cell-icon"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text">hell</div>
               <div class="grid-cell-price">69420Ft</div>
               <div class="grid-cell-icon lite"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text lite">szikszo</div>
               <div class="grid-cell-price lite">69420Ft</div>
               <div class="grid-cell-icon"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text">hell</div>
               <div class="grid-cell-price">69420Ft</div>
               <div class="grid-cell-icon lite"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text lite">szikszo</div>
               <div class="grid-cell-price lite">69420Ft</div>
               <div class="grid-cell-icon"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text">hell</div>
               <div class="grid-cell-price">69420Ft</div>
               <div class="grid-cell-icon lite last"><img src="favicon.png" alt=""></div>
               <div class="grid-cell-text lite last">szikszo</div>
               <div class="grid-cell-price lite last">69420Ft</div>
            </div>
         </div>
      {/if}
      {#if navigation == "pogi"}
         <div in:fly={flyIn} out:fly={flyOut} class="inner-div">
            <p style="display: flex; height: 100vh; width: 100vw; justify-content: center; align-items: center;">pogi</p>
         </div>
      {/if}
   </div>

</main>

<style lang="scss">
   :global(*) {
      margin: 0;
      padding: 0;
      list-style: none;
      text-decoration: none;
   }

   .nav {
      display: flex;
      background-color: orange;
      height: 12vh;
      width: 100vw;
      position: fixed;
      bottom: 0;
      left: 0;
      z-index: 20;

      div {
         display: flex;
         flex: 33.3%;
         justify-content: center;
         align-items: center;
      }

      .active {
         padding: 2vh;
         background-color: rgb(255, 166, 0);
         border-radius: 2vh;
         animation:shadow-drop-2-center .2s forwards
      }
   }

   /* ----------------------------------------- */

// Cleaned up the SCSS a bit since you're already using SCSS (I'm a big SCSS fan myself)
   .outer-div {
      display: grid;
      
      .inner-div {
         // Using grid and grid-area 1/1 to force the inner divs into the same area. 
         // If you don't do this you get a bouncing effect where the incoming div is
         // pushed below the outgoing div and then "pops up" jarringly.
         grid-area: 1/1;	

         .grid-container {
            background: red; // Made background red just see things easier. Do whatever you want here.
            display: grid;
            grid-template-columns: 25vw auto auto 15.2vw;
            border-top: solid .2vw grey;
            border-bottom: solid .2vw grey;
            margin-top: 5vh;
            margin-bottom: 20vh;

            div {
               display: flex;
               justify-content: center;
               align-items: center;
               border-bottom: .1vw solid rgb(201, 201, 201);
            }

            .grid-cell-price {
               justify-content: left;
               font-style: italic;
               font-size: 80%;
               color: rgba(0, 0, 0, 0.774);
            }

            .grid-cell-text {
               grid-column-start: 2;
               grid-column-end: 4;
            }

            .grid-cell-icon {
               img {
                  width: 100%;
                  display: block;
                  margin: auto;
               }
            }


            .last {
               border-bottom: none;
            }

            .lite {
               background-color: rgb(245, 245, 245);
            }
         }
      }
   }



   @keyframes shadow-drop-2-center{0%{transform:translateZ(0);box-shadow:0 0 0 0 transparent}100%{transform:translateZ(50px);box-shadow:0 0 1vw 0 rgba(0,0,0,.35)}}
</style>
