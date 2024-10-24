<script>
    import Body from "./body.svelte";
    import Header from "./header.svelte";
    import Nav from "./nav.svelte";
</script>

<svelte:head>
    <link
        rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
    />
</svelte:head>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
    href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400..900&family=Russo+One&display=swap"
    rel="stylesheet"
/>
<Header />
<Nav />
<Body />
