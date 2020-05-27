<script>
  import { fade } from "svelte/transition";
  import { swedish } from "../henkeData.js";

  const { about } = swedish;
</script>

<div in:fade="{{ duration: 750 }}">
  {#each about as line}
    <p>{line}</p>
  {/each}
  <img src="../../smilingHenke.jpg" alt="A picture of Henrik smilling" />
</div>

<style>
  img {
    margin-top: 3rem;
    margin-bottom: 8rem;
    width: 250px;
    height: auto;
  }

  @media (min-width: 640px) {
    img {
      width: inherit;
      height: inherit;
    }
  }
</style>
