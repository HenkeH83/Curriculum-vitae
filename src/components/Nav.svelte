<script>
  import { onMount } from "svelte";

  export let segment;

  let windowWidth;
  let isVisible = false;

  onMount(async () => {
    isVisible = (await window.innerWidth) > 760;
    window.addEventListener("resize", handleResize);
  });

  const handleResize = () => {
    isVisible = window.innerWidth > 760;
  };

  const toggleIsVisible = () => (isVisible = !isVisible);
</script>

<nav>
  <h4 class="theBurger mobileMeny" on:click="{toggleIsVisible}">&#9776;</h4>
  {#if isVisible}
    <div class="theList mobileMeny">
      <ul>
        <li>
          <img src="../../hh-logga-big.png" alt="Loggo" />
        </li>
        <li>
          <a
            aria-current="{segment === undefined ? 'page' : undefined}"
            href="."
          >
            Om mig
          </a>
        </li>
        <li>
          <a
            aria-current="{segment === 'Experience' ? 'page' : undefined}"
            href="Experience"
          >
            Erfarenheter
          </a>
        </li>
        <li>
          <a
            aria-current="{segment === 'Contact' ? 'page' : undefined}"
            href="Contact"
          >
            Kontakt
          </a>
        </li>
      </ul>
    </div>
  {/if}
</nav>

<style>
  @import "../../global.css";

  a {
    font-weight: 300;
    border: 0;
    padding: 3px;
    border-radius: 5px;
    outline: none;
  }

  nav {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  img {
    height: 3rem;
  }

  .theList {
    bottom: 5rem;
    border-radius: 5px;
  }

  .theList > ul {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .theList > ul > li {
    margin-bottom: 1rem;
    padding: 1rem;
  }

  .theBurger {
    bottom: 0;
    padding: 0.5rem;
    border-radius: 100px;
  }

  .mobileMeny {
    position: fixed;
    background-color: rgba(199, 199, 199, 0.8);
    z-index: 1;
    backdrop-filter: blur(5px);
  }

  ul {
    margin: 0;
    padding: 0;
  }

  [aria-current] {
    position: relative;
    display: inline-block;
  }

  [aria-current]::after {
    position: absolute;
    content: "";
    width: calc(100%);
    height: 2px;
    background-image: linear-gradient(to right, #da9d41, var(--accentColor));
    display: block;
    bottom: -1px;
  }

  @media (min-width: 760px) {
    a {
      font-size: 100%;
      transition: font-size 0.3s, border 0.2s;
    }

    a:hover {
      cursor: pointer;
      font-size: 110%;
      opacity: 0.7;
    }

    li:hover {
      margin: 0;
    }

    nav {
      border-bottom: 1px solid rgb(103, 153, 165);
      flex-direction: row;
      align-items: center;
    }

    .theList {
      background-color: inherit;
      padding-left: 1rem;
      padding-right: 1rem;
      z-index: inherit;
      position: inherit;
      bottom: inherit;
      width: 100%;
      border-radius: 2px;
    }

    .theList > ul {
      flex-direction: row;
      justify-content: space-around;
      align-items: baseline;
      margin: 0.5rem -0.7rem 0.3rem -0.7rem;
    }

    .theList > ul > li {
      margin-bottom: inherit;
      font-size: 1.6rem;
    }

    .theBurger {
      display: none;
    }
  }
</style>
