<script>
	let count = 0;
	const inCrementCount = () => {
		count += 1;
	};
	const deCrementCount = () => {
		count -= 1;
	};
</script>

<svelte:head>
	<title>test</title>
	<meta name="description" content="test this app" />
</svelte:head>

<div>
	<h1>ああ</h1>
	<h1> {count} </h1>
	<p><button on:click={inCrementCount}>Increment</button></p>
	<p><button on:click={deCrementCount}>Increment</button></p>
</div>
