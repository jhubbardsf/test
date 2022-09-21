<script>
   import { swipe } from "svelte-gestures";
   import { slide, fade, fly } from "svelte/transition";
   let navigation = "szendvics";
</script>

   <main>

      <div class="nav">
         <div class="szendvics" on:click={() => {}}><p class="active">szendvics</p></div>
         <div class="ital" on:click={() => {location = "ital"}}><p>ital</p></div>
         <div class="pogi" on:click={() => {location = "pogi"}}><p>pogi</p></div>
      </div>

   <div class="grid-container">
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

   .grid-container {
      display: grid;
      grid-template-columns: 25vw auto auto 15.2vw;
      border-top: solid .2vw grey;
      border-bottom: solid .2vw grey;
      margin-top: 5vh;
      margin-bottom: 20vh;
      height: 100wh;
      width: 100wv;
   }

   .grid-cell-icon {
      img {
         width: 100%;
         display: block;
         margin: auto;
      }
   }

   .grid-cell-text {
      grid-column-start: 2;
      grid-column-end: 4;
   }

   .grid-cell-price {
      font-style: italic;
      font-size: 80%;
      color: rgba(0, 0, 0, 0.774);
   }

   .grid-container {
      div {
         display: flex;
         justify-content: center;
         align-items: center;
         border-bottom: .1vw solid rgb(201, 201, 201);
      }

      .grid-cell-price {
         justify-content: left;
      }

      .last {
         border-bottom: none;
      }

      .lite {
         background-color: rgb(245, 245, 245);
      }
   }

   // animation----------------------------

 @keyframes shadow-drop-2-center{0%{transform:translateZ(0);box-shadow:0 0 0 0 transparent}100%{transform:translateZ(50px);box-shadow:0 0 1vw 0 rgba(0,0,0,.35)}}
</style>