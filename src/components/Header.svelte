<script>

</script>

<header>
  <h1 class="first">Henrik</h1>
  <h1 class="last inverted">Hagström</h1>
</header>

<style>
  @import "../../global.css";

  header {
    display: flex;
    justify-content: center;
  }

  h1 {
    font-size: 1rem;
    letter-spacing: 0.7rem;
    padding-top: 0.5rem;
    padding-bottom: 0.5rem;
  }

  .first {
    border: 1px solid var(--textColor);
    border-bottom-left-radius: 2px;
    border-top-left-radius: 2px;
    border-right: none;
    padding-left: 1rem;
  }

  .last {
    border-top-right-radius: 2px;
    border-bottom-right-radius: 2px;
    padding-right: 1rem;
  }

  @media (min-width: 480px) {
    h1 {
      font-size: 2rem;
    }
  }

  @media (min-width: 760px) {
    h1 {
      font-size: 3rem;
    }
  }
</style>
