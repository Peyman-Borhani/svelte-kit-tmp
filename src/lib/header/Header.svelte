<script>
	import 	{page}	from	'$app/stores';
	import   logo	from	'./svelte-logo.svg';

</script>



<header>
  <div  class = 'left' >
		<a   href = 'https://kit.svelte.dev'>	
					<img src = {logo} 	alt='SvelteKit' />
		</a>
		<a   href = 'https://kit.svelte.dev'>	
			<img src = {logo} 	alt='SvelteKit' />
</a>		<a   href = 'https://kit.svelte.dev'>	
	<img src = {logo} 	alt='SvelteKit' />
</a>
  </div>

  <nav>
	<svg  viewBox='0 0 2 3'  aria-hidden='true'>  <path d='M0,0 L1,2 C1.5,3 1.5,3 2,3 L2,0 Z'/>
	</svg>
	
	<ul>
		<li class:on={$page.path === '/'}>		<a sveltekit:prefetch href='/'> 	Home </a> </li>
		<li class:on={$page.path === '/about'}> <a sveltekit:prefetch href='/about'>About</a> </li>
		<li class:on={$page.path === '/todos'}> <a sveltekit:prefetch href='/todos'>Todos</a> </li>
	</ul>
	
	<svg  viewBox='0 0 2 3'  aria-hidden='true'>  <path d='M0,0 L0,3 C0.5,3 0.5,3 1,2 L2,0 Z'/>
	</svg>
	
  </nav>

	<div class='right'>	<!-- TODO put something else here? github link? -->
		<a   href = 'https://kit.svelte.dev'>	
			<img src = {logo} 	alt='SvelteKit' />
		</a>

	</div>

</header>


<style>
	
	header	{	
				display: flex;			position: absolute;		
				width: 100%;			flex-direction: column; 
				user-select: none;		align-items: center;
										justify-content: space-between;
	}
	header:hover .left, .right{ height: fit-content }

	.left, .right { display: flex;			
					z-index: 1; 		position: absolute;
	}

	.left	{ align-self: flex-start;	flex-direction: column }
	.right	{ align-self: flex-end;		flex-direction: row }

	.right img,
	.left img  { 
				width : 3ch;			padding: .6ch 1ch;
				height: 3ch;			object-fit: contain;
	}

	nav		{	
				display: flex;		 	justify-content: center;
				position: absolute;	 	transition: margin 0.3s ease-out;
				margin: -3vh 0;			--navBKG: #0002; 
				padding: 1pt;			z-index: 1;
								height: 12vh;
	}


	nav:hover {  margin-top: 0;  		border: 9ch solid transparent;
				 --navBKG:#fff9;  border-top: .8ch solid #216;
	}

	path	{  fill: var(--navBKG)	}

	ul		{	
				display: flex;			justify-content: space-between;
				margin: 0;				background-size: contain; 
				padding: 0;				background: var(--navBKG);
				list-style: none;		border-bottom: 1px solid #0001;
	}


	nav li	{ align-self: flex-end;  line-height: 3ch;	position: relative }
	nav li.on {  border-bottom: 1px solid var(--accent-color)  }

	nav:hover li a { opacity: 1;	     font-size: 1.9ch;
					color: initial;     text-decoration: none !important
	} 


	nav li a 	{	
				display: flex;			align-items: center; 
				height: 100%;			color: var(--heading-color);
				padding: 0 3ch;			text-transform: uppercase;
				letter-spacing: 1pt;	text-decoration: none;
				font-weight: 700;		text-shadow: 0 0 1px #000;
				font-size: 1.5ch;		transition: color .2s ease-out;
										opacity: .6;
	}

	nav:hover li.on::before {	
				--size: 6pt;			position: absolute;
				content: '';			left: calc(50% - var(--size));	
				top: -2ch;				border: var(--size) solid transparent;
										border-top: var(--size) solid var(--accent-color);
	}

	nav:hover a:hover { color: var(--accent-color);text-shadow: 0 0 1.6pt  #000; }


</style>
