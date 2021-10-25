<script>
	import { spring } from 'svelte/motion';

	let count = 0;

	const displayed_count = spring();
	$: displayed_count.set(count);
	$: offset = modulo($displayed_count, 1);

	// handle negative numbers
	function modulo(n, m) {return ((n % m) + m) % m;} 
		
</script>

<div  class = "counter">
	<button  on:click={() => (count -= 1)} aria-label="Decrease the counter by one">
		<svg aria-hidden="true" viewBox="0 0 1 1">	<path d="M0,0.5 L1,0.5" />
		</svg>
	</button>

	<div class="counter-viewport">
		<div class="counter-digits"  style="transform: translate(0, {100 * offset}%)">
			<strong  style="top: -100%" aria-hidden="true">  {Math.floor($displayed_count + 1)}
			</strong>
			<strong>  {Math.floor($displayed_count)}  </strong>
		</div>
	</div>

	<button  on:click  =  {()=> (count += 1)}   
		     aria-label= "Increase the counter by one">
			<svg  aria-hidden="true" viewBox="0 0 1 1" >
				  <path  d="M0,0.5 L1,0.5 M0.5,0 L0.5,1" />
			</svg>
	</button>
</div>

<style>
.counter {	
			display: flex;
			height: 6ch;	 	border-top: 1px solid rgba(0, 0, 0, 0.1);
			margin: 1ch 0;		border-bottom: 1px solid rgba(0, 0, 0, 0.1);
	}

.counter button {
			display: flex;		align-items: center;
			width: 2em;			justify-content: center;
			padding: 0;			font-size: 2rem;
			border: 0;			color: var(--text-color);
								background-color: transparent;	
	}

	.counter button:hover { background-color: var(--secondary-color); }

	svg {	width: 30%;			height: 30%; 	}

	path {	vector-effect: non-scaling-stroke;
			stroke-width: 2px;
			stroke: var(--text-color);
	}

	.counter-viewport {
					width: 8em;			overflow: hidden;
					height: 4em;		text-align: center;
										position: relative;
	}

	.counter-viewport strong {
				display: flex;			align-items: flex-start;
				position: absolute;		justify-content: center;
				width: 100%;			font-weight: 400;
				height: 100%;			font-size: 3ch;
										color: var(--accent-color);
		
		
	}

	.counter-digits {	width: 100%;		position: absolute;
						height: 100%;
	}

</style>
