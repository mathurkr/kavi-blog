<script>
    import "../styles/tailwind-output.css";
</script>

<div class="bg-gradient-to-r from-slate-500 to-blue-500">
    <img src="static/favicon.png">
    <h1 class="text-lg text-center">Kavi Mathur</h1>
    <nav class="text-center">
        <a href="/" class="text-center">Home</a>
    </nav>
    <main class="mx-20 ">
        <slot />
    </main>

</div>