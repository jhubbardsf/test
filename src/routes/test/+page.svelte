<script>
   import { slide, fade, fly } from "svelte/transition";
   let navigation = "szendvics";
</script>
<main>

<div class="nav">
   <div class="szendvics" on:click={() => {navigation = "szendvics"}}><p class:active="{navigation == "szendvics"}">left</p></div>
   <div class="ital" on:click={() => {navigation = "ital"}}><p class:active="{navigation == "ital"}">right</p></div>
   <div class="pogi" on:click={() => {navigation = "pogi"}}><p class:active="{navigation == "pogi"}">pogi</p></div>
</div>

{#if navigation == "szendvics"}
<div in:fly={{x: -200, duration: 200}} class="maindiv">
   <p>szendvics</p>
</div>
{/if}
{#if navigation == "ital"}
<div in:fly={{x: 200, duration: 200}} class="maindiv">
   <p>ital</p>
</div>
{/if}
{#if navigation == "pogi"}
<div in:fly={{x: 200, duration: 200}} class="maindiv">
   <p>pogi</p>
</div>
{/if}

</main>

<style>
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
      width: 100%;
      position: fixed;
      bottom: 0;
      left: 0;
      z-index: 20;
	}
      .nav div {
         display: flex;
         flex: 33.3%;
         justify-content: center;
         align-items: center;
      }

      .nav .active {
         padding: 2vh;
         background-color: rgb(255, 166, 0);
         border-radius: 2vh;
         animation:shadow-drop-2-center .2s forwards
      }

   .maindiv {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 10vh;
   }

 @keyframes shadow-drop-2-center{0%{transform:translateZ(0);box-shadow:0 0 0 0 transparent}100%{transform:translateZ(50px);box-shadow:0 0 1vw 0 rgba(0,0,0,.35)}}
</style>