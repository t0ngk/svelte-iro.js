<script lang="ts">
	import Iro from '$lib/Iro.svelte';
	let color = '#FE0000';
	let setColor: any;
</script>

<div>
	<Iro bind:color bind:setColor />
</div>

<div style={`width: 50px; height: 50px; background-color: ${color};`}>

</div>

<button on:click={() => (setColor("#FFF"))}> White</button>
<button on:click={() => (setColor("#000"))}> Black</button>
<button on:click={() => (setColor("#FE0000"))}> Red</button>
<button on:click={() => (setColor("#00FE00"))}> Green</button>
<button on:click={() => (setColor("#0000FE"))}> Blue</button>
