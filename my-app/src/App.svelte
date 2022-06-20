<script>
  import Input from "./input.svelte";
  import logo from "./assets/svelte.png";
  import Counter from "./lib/Counter.svelte";

  //console.log(gun.get('/'));

  var a = "mono";
  var n = 1;
  function cambiaNombre() {
    a = "xxxxa";
    n++;
  }

  // reactive
  $: {
    if (n > 9) {
      n = 9;
    }
  }
</script>

<main>
  <img src={logo} alt="Svelte Logo" />
  <h1>Hola world! {a} {n * 1}</h1>

  {#if n < 5}
    <strong> menos de 5</strong>
  {:else if n > 5}
    <strong> n mas 5</strong>
  {/if}
  <!--fin condicion -->

  <button on:click={cambiaNombre}> cambiar nombre </button>
  <Counter />
  <Input />
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  img {
    height: 16rem;
    width: 16rem;
  }

  h1 {
    color: #ff0040;
    text-transform: uppercase;
    font-size: 4rem;
    font-weight: 100;
    line-height: 1.1;
    margin: 2rem auto;
    max-width: 14rem;
  }

  p {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
  }

  @media (min-width: 480px) {
    h1 {
      max-width: none;
    }

    p {
      max-width: none;
    }
  }
</style>
