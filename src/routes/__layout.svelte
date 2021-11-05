
<script>	

	import		Header		from	'$lib/header/Header.svelte';
	import 		{page}		from	'$app/stores';
	import		{fly}		from	'svelte/transition';
	import		'../app.css';
	
	$: x = $page.path;

</script>

<!-- In "__Layout" we include styles and components the app has in common,
	 which applies to all pages. (Ex: header, footer, main, theme, color...)
	 
	 and individual pages/content resides in the <slot>
	 slot is place-holder for our dynamic content (app pages in the route), 
	 in this example contents/pages are placed within the "main" element as "slot"
-->
<Header />

{#key x}
		<main 	in:fly = {{y: -8, duration: 700}} >

				<slot />
		</main>
{/key}


<footer>
	<p> visit 	<a href="https://kit.svelte.dev"> kit.svelte.dev </a>  
		to learn SvelteKit 
	</p>
</footer>


<style>

	main	{	display: flex;			flex-direction: column;
				flex: 1;				margin: 9vh auto;
				width: 98vw;			max-width: 1024px;
							box-sizing: border-box;
				overflow-y: auto;		
	}

	footer	{	display: flex;			flex-direction: column;
				align-items: center;	justify-content: center;
										justify-self: flex-end;	
	}

	footer p {  text-align: center }
	footer a {	font-weight: bold  }

	@media (max-width: 480px) {
			footer { padding: 4pt }
	}

	::-webkit-scrollbar { width: 1vw }
	::-webkit-scrollbar-thumb { 
								border-radius: 2pt;     
								min-height: 18pt;
                                background   : #cceeff66;
                                box-shadow: inset 0 0 2pt #99cd;
	}
	::-webkit-scrollbar-track {	
								background: linear-gradient(#defb, transparent);
                                border-radius: 2pt; 
                                box-shadow: inset 0 0 2pt #678a; 
	}

</style>
