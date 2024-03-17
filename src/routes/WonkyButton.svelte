<script>
	import { createEventDispatcher } from 'svelte';
	
  export let value = 0;
	let random = 0;

	const dispatch = createEventDispatcher();

	function handleClick() {
		random = Math.floor(Math.random() * 10);
		value += random;

		dispatch('updateSum');
	}
</script>

<button on:click={handleClick}>
	{#if value % 3 == 0 && value % 5 == 0}
		{'FizzBuzz ' + value}
	{:else if value % 3 == 0}
		{'Fizz ' + value}
	{:else if value % 5 == 0}
		{'Buzz ' + value}
	{:else}
		{value}
	{/if}
</button>
