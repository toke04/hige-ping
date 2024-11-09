<script>
	import { writable } from "svelte/store";
	let input = '';
	let markIndex = 0;
	let finishWord = writable('');
	let questions = ['aaa', 'bbb', 'ccc', 'ddd'];
	let question = questions[Math.floor(Math.random() * questions.length)];

	// $: changeQuestion(finishWord);

	const changeQuestion = () => {
		question = questions[Math.floor(Math.random() * questions.length)];
		setTimeout(() => {
			finishWord = '';
		}, 1000);
	};

	const handleKeydown = (e) => {
		if (e.key === question[markIndex]) {
			markIndex++;
			input += e.key;
			if (markIndex === question.length) {
				finishWord = '正解！';
				markIndex = 0;
				changeQuestion();
			}
		}
	};
</script>
<svelte:window on:keydown={handleKeydown} />
<svelte:head>
	<title>test</title>
	<meta name="description" content="test this app" />
</svelte:head>

<div>
	{#if finishWord}
		<h1 class="text-red-900">{ finishWord }</h1>
	{/if}
	<h1>
		{#each question.split('') as q,i}
			<span class={i === markIndex ? 'text-red-900' : '' }>{q}</span>
		{/each}
	</h1>
	<h1>今まで打った内容:{ input }</h1>
<!--	<p><button on:keydown={handleKey}>ボタンを押して</button></p>-->

<!--	<p>-->
<!--		<button-->
<!--			on:click={deCrementCount}-->
<!--			class="mb-2 rounded-lg bg-purple-700 px-5 py-2.5 text-sm font-medium text-white hover:bg-purple-800 focus:outline-none focus:ring-4 focus:ring-purple-300 dark:bg-purple-600 dark:hover:bg-purple-700 dark:focus:ring-purple-900"-->
<!--			>Increment</button-->
<!--		>-->
<!--	</p>-->
</div>
