<svelte:head>
    <title>Blog</title>
</svelte:head>


<script context="module" lang="ts">
    const blogPosts=import.meta.glob('./*.svx')

    let body = [];

    for (const path in blogPosts){
        body.push(blogPosts[path]().then(({metadata})=>metadata));
    }

    export async function load({ page, fetch }) {
    const posts = await Promise.all(body) //Waiting for all blog posts to load their data
    return {
      props: { // Stores all blog posts as a prop
        posts
      }
    };
  }
</script>
<script lang="ts">
    import Tag from "$lib/Tag.svelte";
    export let posts;
</script>
<div class="font-sans">
    <h1 class="tracking-widest font-sans break-normal text-white pt-6 pb-2 text-3xl md:text-4xl">
      Recent posts
    </h1>
  
    <ul class="list-none">
      {#each posts as {title, tags, outline, slug}}
      <li class="list-none">
        <a
          class="text-blue-500 space-y-3"
          rel="prefetch"
          href="blog/{slug}"
        >
          <h2>
            {title}
          </h2>
  
          <p class="text-white text-base">
            {outline}
          </p>
  
          <p class="text-sm font-normal text-gray-500">
            Tags: {#each tags as tag}
              <Tag { tag }/>
            {/each}
          </p>
        </a>
      </li>
      {/each}
    </ul>
</div>