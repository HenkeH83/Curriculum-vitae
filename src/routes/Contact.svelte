<script>
  import { fade } from "svelte/transition";
  import { swedish } from "../henkeData.js";

  const { contact } = swedish;
</script>

<div class="container">
  <div class="contacts" in:fade="{{ duration: 750 }}">
    {#each contact as item}
      {#if item.id === 'mail'}
        <a href="mailto:{item.link}">
          <div class="linkContainer">
            <img src="../../icon_mail_64.png" alt="Mail icon" />

            <h3>{item.text}</h3>
          </div>
        </a>
      {:else}
        <a href="{item.link}" rel="noopener" target="blank">
          <div class="linkContainer">
            {#if item.id === 'twitter'}
              <img src="../../icon-twitter_64.png" alt="Twitter icon" />
            {:else if item.id === 'linkedin'}
              <img src="../../icon_linkedin_64.png" alt="LinkedIn icon" />
            {/if}
            <h3>{item.text}</h3>
          </div>
        </a>
      {/if}
    {/each}
  </div>
</div>

<style>
  .container {
    display: flex;
    justify-content: center;
  }

  .contacts {
    display: flex;
    flex-direction: column;
  }

  .linkContainer {
    display: flex;
    flex-direction: row;
    align-items: center;
  }

  img {
    height: 2rem;
    margin: 0 1rem 0 0;
  }

  @media (min-width: 760px) {
    .linkContainer {
      transition: 300ms;
    }

    .linkContainer:hover {
      opacity: 0.7;
      font-size: 110%;
    }
  }
</style>
