<script>
    let count = 0;

	function incrementCount() {
		count += 1;
	}    

	$: doubled = count * 2;

	$: if (count >= 10) {
		//console.log(`the count is ${count}`);
		alert(`I SAID THE DOUBLE IS ${count}` );
		count = 9;
	}    
</script>

<p>{count} doubled is {doubled}</p>

<button on:click={incrementCount}> Clicked {count} {count === 1 ? 'time' : 'times'} </button>