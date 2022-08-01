<script>
    import { onMount } from 'svelte';
    import { posts } from './posts.js';
    import { Converter } from 'showdown';
    import './css/index.css';
    const converter = new Converter();
  
</script>

<div id="posts">
    {#each posts as post}
      <article>
        <h1>{post.title}</h1>
        <h2>by {post.author}</h2>
        {#if post.type == "text"}
          <p>{@html converter.makeHtml(post.content)}</p>
        {:else}
          {#await fetch("./posts/" + post.content + ".md") then response}
            {#await response.text() then content}
              <p>{@html converter.makeHtml(content)}</p>
            {/await}
          {/await}
        {/if}
      </article>
    {/each}
  </div>