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
	<h1>{count}</h1>
	<p><button on:click={inCrementCount}>Increment</button></p>
	<p>
		<button
			on:click={deCrementCount}
			class="mb-2 rounded-lg bg-purple-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-purple-800 focus:outline-none focus:ring-4 focus:ring-purple-300 dark:bg-purple-600 dark:hover:bg-purple-700 dark:focus:ring-purple-900"
			>Increment</button
		>
	</p>
</div>
