<script lang="ts">
	import './layout.css';
	let { children } = $props();
</script>

<svelte:head>
  <link rel="icon" href="imgs/favicon.ico" />
  <link rel="icon" href="imgs/favicon.png" />
  <link rel="icon" href="imgs/favicon.svg" />
  <meta name="description" content="Ọkpan brings together records of artefacts scattered across museums worldwide, reconnecting them with the communities, knowledge, and histories they were separated from." />
  <meta name="keywords" content="Ọkpan, tool, museums collections">
  <meta name="author" content="Calibro" />
  <link rel="canonical" href="https://domain.ext" />
  <meta property="og:locale" content="en_US" />
  <meta property="og:type" content="website" />
  <meta property="og:title" content="Ọkpan - A tool for reconnecting dispersed collections" />
  <meta property="og:description" content="Ọkpan brings together records of artefacts scattered across museums worldwide, reconnecting them with the communities, knowledge, and histories they were separated from." />
  <meta property="og:url" content="https://domain.ext/" />
  <meta property="og:site_name" content="Ọkpan - A tool for reconnecting dispersed collections" />
  <meta property="og:image" content="imgs/og-img.jpg" />
  <meta name="apple-mobile-web-app-title" content="Ọkpan" />
  <meta name="application-name" content="Ọkpan" />
  <meta name="msapplication-TileColor" content='#FFFFFF' />
</svelte:head>

{@render children()}
