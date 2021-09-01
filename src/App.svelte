<script>
	import Nested from './Nested.svelte';
	import Test from './Test.svelte';
	import PlusAValue from './PlusAValue.svelte';
	let src = 'tutorial/image.gif';
	let name = 'Rick Astley';

	let count = 0;
	$: doubled = count * 2;
	
	function incrementCount() {
		count += 1;
	}

	$: if (count >= 10) {
		//console.log(`the count is ${count}`);
		alert(`I SAID THE DOUBLE IS ${count}` );
		count = 9;
	}

	let numbers = [1,2,3,4];

	function addNumber() {
		numbers.push(numbers.length + 1);
		numbers = numbers;
	}

	$: sum = numbers.reduce((t, n) => t + n, 0);

	


</script>
<PlusAValue />
<Test />
<h1>Hello {name.toUpperCase()}!</h1>

<p>{numbers.join(' + ')} = {sum} </p>

<img {src} alt="{name} dances.">
<Nested />

<button on:click={addNumber}>
	Add a number
</button>

<button on:click={incrementCount}> Clicked {count} {count === 1 ? 'time' : 'times'} </button>

<p>{count} doubled is {doubled}</p>


