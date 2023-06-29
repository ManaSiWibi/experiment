<script>
	let m = { x: 0, y: 0 };

	function closeWindow() {
		close();
	}
</script>

<svelte:window on:keydown={closeWindow} />


<div class="flex justify-center items-center h-screen">
    <button class="px-4 py-2 bg-gray-500 text-white rounded hover:bg-gray-600 focus:outline-none" on:click={closeWindow}>
      Click to Die!
    </button>
  </div>