<script>
	import Book from '../book/+page.svelte'
	let books = [
		{title: 'hoge1', content: 'ああ'},
		{title: 'hoge2', content: 'いい'},
		{title: 'hoge3', content: 'うう'},
		{title: 'hoge4', content: 'ええ'},
	]
</script>

<ul>
	{#each books as book}
		<Book book={book}></Book>
	{/each}
</ul>
