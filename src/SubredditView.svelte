<script>
  const BASE_URL = "https://cors-anywhere.herokuapp.com/https://reddit.com/r/";
  const APPEND = "/.json";

  export let subreddit;

  let posts;
  let errored = false;

  $: fetch(BASE_URL + subreddit + APPEND)
    .then(r => r.json())
    .then(d => {
      posts = d.data.children;
    })
    .catch(() => (errored = true));
</script>

<main>
  <h2>Viewing {subreddit}</h2>
  {#if errored}An error occurred{/if}
  {#if posts}
    Loaded data
    {#each posts as post}
      <h3>{post.data.title}</h3>
    {/each}
  {:else}Loading data{/if}
</main>
