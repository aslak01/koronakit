<script>
  import Charts from '$lib/Charts.svelte'
  import MiniWorld from '$lib/components/MiniWorld.svelte'
</script>

<main>
  <header>
    <article class="text">
      <h1 class="header">Corona virus in the world</h1>
    </article>
    <MiniWorld />
  </header>

  <section>
    <Charts />
  </section>

  <footer>
    <article class="text">
      <p>
        Data is automatically updated with numbers from the <a
          href="https://coronavirus.jhu.edu">Johns Hopkins database (JHUCSSE)</a
        >. They collect data from various public databases, which are not always
        in agreement one with the other, which sometimes leads to discrepancies
        and erroneous data.
      </p>
    </article>
  </footer>
</main>

<style>
  main {
    /* max-width: 100%; overflow-x: hidden; */
    min-height: 100vh;
    max-width: 1200px;
    margin: 0 auto;
  }
  section,
  header,
  footer {
    max-width: 80vw;
    margin: 0 auto;
  }

  h1 {
    padding-top: 100px;
  }

  h1.header {
    display: inline;
    font-size: 2rem;
  }

  article.text {
    width: 80vw;
    margin: 0 auto;
    height: auto;
    padding-bottom: 1.5rem;
    padding-top: 3rem;
  }
  a {
    color: hsl(123, 50%, 50%);
    text-decoration: none;
  }
  a:visited {
    color: hsl(123, 50%, 50%);
  }
  a:hover {
    text-decoration: underline;
  }
  footer p {
    font-size: 0.7rem;
  }
</style>
