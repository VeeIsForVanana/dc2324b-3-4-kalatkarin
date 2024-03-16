<script>
  export let value = 0;
	let random = 0;

	function handleClick() {
		random = Math.floor(Math.random() * 10);
		value += random;
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
