<script>
	import { IncrementStencilOp } from 'three';

	let gridSize = 14;
	let dotSize = 1.5;

	let m = { x: 0, y: 0 };

	function closeWindow() {
		close();
	}

	let blip = 0;
	const incr = () => (blip = Math.random());

	setInterval(() => {
		incr();
	}, 500);
</script>

<svelte:window on:keydown={closeWindow} />

<div class="flex justify-center items-center h-screen">
	<div class="h-full w-full absolute">
		<svg width="100%" height="100%" fill="none" xmlns="http://www.w3.org/2000/svg">

      <!-- <pattern id="dot-grid" x="0" y="0" width="64" height="64" patternContentUnits="userSpaceOnUse" patternUnits="userSpaceOnUse"><rect x="3" y="3" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="3" y="11" width="2" height="2" fill="#CDCDCB" opacity="0.5642781630862719"></rect><rect x="3" y="19" width="2" height="2" fill="#CDCDCB" opacity="0.4393742834655985"></rect><rect x="3" y="27" width="2" height="2" fill="#CDCDCB" opacity="0.43053689666054307"></rect><rect x="3" y="35" width="2" height="2" fill="#CDCDCB" opacity="0.3666628277324968"></rect><rect x="3" y="43" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="3" y="51" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="3" y="59" width="2" height="2" fill="#CDCDCB" opacity="0.783003228042"></rect><rect x="11" y="3" width="2" height="2" fill="#CDCDCB" opacity="0.30016781192982156"></rect><rect x="11" y="11" width="2" height="2" fill="#CDCDCB" opacity="0.4029345990071146"></rect><rect x="11" y="19" width="2" height="2" fill="#CDCDCB" opacity="0.25333905507492205"></rect><rect x="11" y="27" width="2" height="2" fill="#CDCDCB" opacity="0.4456522084375035"></rect><rect x="11" y="35" width="2" height="2" fill="#CDCDCB" opacity="0.2875608809431578"></rect><rect x="11" y="43" width="2" height="2" fill="#CDCDCB" opacity="0.6652233725967053"></rect><rect x="11" y="51" width="2" height="2" fill="#CDCDCB" opacity="0.8789391359720956"></rect><rect x="11" y="59" width="2" height="2" fill="#CDCDCB" opacity="0.8747633846169246"></rect><rect x="19" y="3" width="2" height="2" fill="#CDCDCB" opacity="0.8883183263576523"></rect><rect x="19" y="11" width="2" height="2" fill="#CDCDCB" opacity="0.6403157580792092"></rect><rect x="19" y="19" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="19" y="27" width="2" height="2" fill="#CDCDCB" opacity="0.5507053101371497"></rect><rect x="19" y="35" width="2" height="2" fill="#CDCDCB" opacity="0.45819090722807043"></rect><rect x="19" y="43" width="2" height="2" fill="#CDCDCB" opacity="0.9931402534519725"></rect><rect x="19" y="51" width="2" height="2" fill="#CDCDCB" opacity="0.6160077089124838"></rect><rect x="19" y="59" width="2" height="2" fill="#CDCDCB" opacity="0.859721805934404"></rect><rect x="27" y="3" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="27" y="11" width="2" height="2" fill="#CDCDCB" opacity="0.9155348315434179"></rect><rect x="27" y="19" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="27" y="27" width="2" height="2" fill="#CDCDCB" opacity="0.6053115040407322"></rect><rect x="27" y="35" width="2" height="2" fill="#CDCDCB" opacity="0.7018890303648697"></rect><rect x="27" y="43" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="27" y="51" width="2" height="2" fill="#CDCDCB" opacity="0.3861887075855035"></rect><rect x="27" y="59" width="2" height="2" fill="#CDCDCB" opacity="0.8017396322974135"></rect><rect x="35" y="3" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="35" y="11" width="2" height="2" fill="#CDCDCB" opacity="0.8327229413632131"></rect><rect x="35" y="19" width="2" height="2" fill="#CDCDCB" opacity="0.5905164290265009"></rect><rect x="35" y="27" width="2" height="2" fill="#CDCDCB" opacity="0.6248479521602709"></rect><rect x="35" y="35" width="2" height="2" fill="#CDCDCB" opacity="0.44692070500982295"></rect><rect x="35" y="43" width="2" height="2" fill="#CDCDCB" opacity="0.41860743421778535"></rect><rect x="35" y="51" width="2" height="2" fill="#CDCDCB" opacity="0.6172105385707471"></rect><rect x="35" y="59" width="2" height="2" fill="#CDCDCB" opacity="0.8683671789523406"></rect><rect x="43" y="3" width="2" height="2" fill="#CDCDCB" opacity="0.5058956675421207"></rect><rect x="43" y="11" width="2" height="2" fill="#CDCDCB" opacity="0.7457628757714976"></rect><rect x="43" y="19" width="2" height="2" fill="#CDCDCB" opacity="0.7840181149490655"></rect><rect x="43" y="27" width="2" height="2" fill="#CDCDCB" opacity="0.5931476496732155"></rect><rect x="43" y="35" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="43" y="43" width="2" height="2" fill="#CDCDCB" opacity="0.26761608690178984"></rect><rect x="43" y="51" width="2" height="2" fill="#CDCDCB" opacity="0.40040087293873705"></rect><rect x="43" y="59" width="2" height="2" fill="#CDCDCB" opacity="0.8197355963586259"></rect><rect x="51" y="3" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="51" y="11" width="2" height="2" fill="#CDCDCB" opacity="0.8491606379683175"></rect><rect x="51" y="19" width="2" height="2" fill="#CDCDCB" opacity="0.5122362594094169"></rect><rect x="51" y="27" width="2" height="2" fill="#CDCDCB" opacity="0.9494902553993018"></rect><rect x="51" y="35" width="2" height="2" fill="#CDCDCB" opacity="0.630507961448373"></rect><rect x="51" y="43" width="2" height="2" fill="#CDCDCB" opacity="0.37339735987795264"></rect><rect x="51" y="51" width="2" height="2" fill="#CDCDCB" opacity="0.8651123650922408"></rect><rect x="51" y="59" width="2" height="2" fill="#CDCDCB" opacity="0.43990295775840826"></rect><rect x="59" y="3" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="59" y="11" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect><rect x="59" y="19" width="2" height="2" fill="#CDCDCB" opacity="0.4593145894655547"></rect><rect x="59" y="27" width="2" height="2" fill="#CDCDCB" opacity="0.5070780223715158"></rect><rect x="59" y="35" width="2" height="2" fill="#CDCDCB" opacity="0.8445569399510043"></rect><rect x="59" y="43" width="2" height="2" fill="#CDCDCB" opacity="0.5725364745116841"></rect><rect x="59" y="51" width="2" height="2" fill="#CDCDCB" opacity="0.7463099522808305"></rect><rect x="59" y="59" width="2" height="2" fill="#CDCDCB" opacity="0.25"></rect></pattern> -->
      <pattern id="dot-grid" x="0" y="0" width="64" height="64" patternContentUnits="userSpaceOnUse" patternUnits="userSpaceOnUse">
        {#each Array(8) as _, i}
					{#each Array(8) as _, j}
						<circle
            fill="#ea1821"
							cx={dotSize + i * dotSize * gridSize}
							cy={dotSize * gridSize * j}
							r={dotSize}
							opacity={blip*2}
						/>
 <circle
          cx={dotSize + i * dotSize * gridSize}
          cy={dotSize * gridSize * j}
          r={dotSize}
          opacity="{blip}}"
        /> 
						<circle
              fill="#EA1821"
							cx={dotSize + i * dotSize * gridSize + 10}
							cy={dotSize * gridSize * j + 8}
							r={(dotSize)}
							opacity={blip}
						/>
					{/each}
				{/each}
      </pattern>
      <rect x="0" y="0" width="100%" height="100%" fill="url(#dot-grid)"></rect>


		</svg>
	</div>

	<button
		class="px-4 py-2 bg-gray-500 text-white rounded hover:bg-gray-600 focus:outline-none"
		on:click={closeWindow}
	>
		Click to Die!{{}}
	</button>
</div>

<style>
  * {
    background-color: #1b1d1c;
    cursor: crosshair;
  }
	circle {
		fill: #ea1821;
	}
</style>
