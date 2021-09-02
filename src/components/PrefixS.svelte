<script>
import { writable } from 'svelte/store';

const count = writable(0);
console.log($count);

count.set(1);
console.log($count);

$count = 2;
console.log($count);

</script>