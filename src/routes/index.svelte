<script   context = "module">
	      export const prerender = true;
</script>


<script >      import   Counter     from  '$lib/Counter.svelte';
</script>


<svelte:head >    <title> Home </title>
</svelte:head>

<section>

		<div class="welcome">
			<picture>
				<source  srcset="svelte-welcome.webp"  type="image/webp" />
				<img     src="svelte-welcome.png"      alt="Welcome" />
			</picture>
		</div>

		<Counter />

		<h1> to your new SvelteKit app  </h1>

		<h2 >  try editing <strong>src/routes/index.svelte</strong>
		</h2>

</section>

<style>
	section {	display: flex;    		flex-direction : column;
			  	flex: 1;				justify-content: center;
										align-items    : center;
}

	h1 {  width: 100%  }

	.welcome { margin: 0 auto; 		position: relative  }

	.welcome img {  width: 100%; 	height: 80%  }
</style>
