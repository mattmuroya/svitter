<script>
  let posts = [{ id: 1, text: 'Hello world!' }];
  let newPost = '';

  const sveet = () => {
    posts = [{ id: posts.length + 1, text: newPost }, ...posts];
    newPost = '';
  };
</script>

<div class="wrapper">
  <header>
    <h1>Svitter</h1>
  </header>
  <main>
    <form on:submit|preventDefault={sveet}>
      <input bind:value={newPost} />
      <button>Sveet</button>
    </form>
    <div class="posts">
      {#each posts as post (post.id)}
        <div class="post">{post.text}</div>
      {/each}
    </div>
  </main>
</div>

<style>
  :global(body),
  :global(html) {
    margin: 0;
  }

  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  .wrapper {
    padding: 40px;
  }

  .posts {
    margin-top: 20px;
  }

  .post {
    margin-top: 10px;
  }
</style>
