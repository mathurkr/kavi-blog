<script>
    import "../styles/tailwind-output.css";
</script>

<div>
    <div class="flex">
        <div class="w-1/6">
            <img alt="svelte logo" src="static/favicon.png">
        </div>
        
        <h1 class="w-5/6 text-2xl text-left">Kavi Mathur</h1>
    </div>

    <nav class="text-center">
        <a href="/">Home</a>
        <a href="/blog">Blog</a>
    </nav>
    <main class="mx-20">
        <slot />
    </main>

</div>