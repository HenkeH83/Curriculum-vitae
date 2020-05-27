<script>
  import { fade } from "svelte/transition";
  import { swedish } from "../henkeData.js";

  const { experience } = swedish;
</script>

<div in:fade="{{ duration: 750 }}">
  {#each experience as xp}
    <div class="card">
      <h2 class="spacing">{xp.titel}</h2>
      <h4 class="spacing">{xp.organization}</h4>
      <h4 class="spacing">{xp.location}</h4>
      <p class="duration spacing">{xp.dateFrom} - {xp.dateTo}</p>
      {#each xp.text as line}
        <p>{line}</p>
      {/each}
    </div>
  {/each}
</div>

<style>
  .spacing {
    margin: 0 0 0.6rem;
  }

  p {
    margin: 0;
  }

  h2 {
    font-weight: 500;
    letter-spacing: 0.1rem;
  }

  h4 {
    font-weight: 500;
    font-style: italic;
  }

  .duration {
    font-size: 1.1rem;
    font-weight: 300;
  }

  .card {
    margin: 2rem 0 4rem 0;
  }
</style>
