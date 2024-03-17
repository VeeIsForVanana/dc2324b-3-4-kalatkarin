<script>
    import WonkyButton from './WonkyButton.svelte';
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    let button_values = [
        {value: 0},
        {value: 0},
        {value: 0},
        {value: 0},
        {value: 0},
    ]

    function fizzBuzz() {
        let sum = 0;

        for (let i = 0; i < button_values.length; i++) {
            sum += button_values[i].value;
        }

        if (sum % 3 == 0 && sum % 5 == 0) {
            dispatch('fizzbuzz', sum);
        }
        else if (sum % 3 == 0) {
            dispatch('fizz', sum);
        }
        else if (sum % 5 == 0) {
            dispatch('buzz', sum);
        }
    }
</script>

{#each button_values as b}
    <WonkyButton on:updateSum={fizzBuzz} bind:value={b.value}/>
{/each}
