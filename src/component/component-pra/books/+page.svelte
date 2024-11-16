<script>
	let books = [
		{title: 'hoge1', content: 'ああ'},
		{title: 'hoge2', content: 'いい'},
		{title: 'hoge3', content: 'うう'},
		{title: 'hoge4', content: 'ええ'},
	]
</script>

<ul>
	{#each books as book}
		<li>タイトル: {book.title} 内容: {book.content}</li>
	{/each}
</ul>
