<script>
	let count = 0;
	let text = 'hello';
	let input = '';
	// const handleKey = (e: React.KeyboardEvent<HTMLDivElement>) => {
	// 	// 入力したキーと現在入力しようとしている文字が一致するとき
	// 	if (e.key === text[position]) {
	// 		// 次の位置へ移動
	// 		setPosition(position + 1);
	// 	}
	// };
	const handleKeydown = (e) => {
		input = e.key;
	};
</script>
<svelte:window on:keydown={handleKeydown} />
<svelte:head>
	<title>test</title>
	<meta name="description" content="test this app" />
</svelte:head>

<div>
	<h1>{ text }</h1>
	<h1>{ input }</h1>
<!--	<p><button on:keydown={handleKey}>ボタンを押して</button></p>-->

<!--	<p>-->
<!--		<button-->
<!--			on:click={deCrementCount}-->
<!--			class="mb-2 rounded-lg bg-purple-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-purple-800 focus:outline-none focus:ring-4 focus:ring-purple-300 dark:bg-purple-600 dark:hover:bg-purple-700 dark:focus:ring-purple-900"-->
<!--			>Increment</button-->
<!--		>-->
<!--	</p>-->
</div>
