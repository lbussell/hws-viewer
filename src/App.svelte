<script>
  import SubredditView from "./SubredditView.svelte";

  let currentSubreddit = "hardwareswap";
</script>

<style>

</style>

<main>
  <h1>Swap Viewer for Reddit</h1>
  <SubredditView subreddit={currentSubreddit} />
</main>
