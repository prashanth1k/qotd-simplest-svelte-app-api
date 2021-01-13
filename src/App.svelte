<script>
  export let quotd = "Patience is the key to good life..";
  export let author = "Unknown";

  const getRandomQuote = () => {
    fetch("https://favqs.com/api/qotd")
      .then(res => res.json())
      .then(data => ([quotd, author] = [data.quote.body, data.quote.author]));
  };
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 3em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <button on:click={getRandomQuote}>Get me a quote!</button>
  <h1>{quotd}</h1>
  <p>- {author} -</p>
</main>
