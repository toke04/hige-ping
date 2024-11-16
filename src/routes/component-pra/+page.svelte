<script>
	import Child from '../../component/component-pra/child1/+page.svelte';
	import Books from '../../component/component-pra/books/+page.svelte';
	import Users from '../../component/component-pra/users/+page.svelte'
	import { onMount } from 'svelte';
	let props = '渡す'
	let users = [
		{name: "taro", age: 18},
		{name: "hanako", age: 49},
		{name: "tomo", age: 37},
	]
	let catImage = ''

	onMount(async () => {
		const res = await fetch('https://api.thecatapi.com/v1/images/search');
		console.log(res.json()) // こういう書き方をするとpromiseが解決しないうちに返却することになるのでpendingになる
		const json = await res.json(); // thenとcatchを兼ねるので、resolveもrejectも受け取れる
		console.log(json[0].url)
		catImage = json[0].url
	})

</script>

<div>
	<h1>ああ</h1>
	<Child name='太郎'/>
	<Child />
	<Child name={props}/>
	<div class="mt-4">
		<Books/>
		<div class="mt-4">
			<Users users={users}/>
		</div>
	</div>
	{#if catImage}
		<p>
				<img src={catImage} alt="猫画像">
		</p>
	{/if}

</div>
