<script>
	import { fly } from 'svelte/transition';
</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<section class="section hero is-medium is-primary is-bold" style="margin-top: 3.25rem">
	<div class="hero-body">
		 <div class="container">
		 	<h1 class="title" in:fly="{{ y: -50, duration: 1000 }}">
				About
			</h1>
		 </div>
	 </div>
</section>
