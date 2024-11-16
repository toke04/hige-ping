<script>
	import Child from '../../component/component-pra/child1/+page.svelte';
	import Books from '../../component/component-pra/books/+page.svelte';
	import Users from '../../component/component-pra/users/+page.svelte'
	let props = '渡す'
	let users = [
		{name: "taro", age: 18},
		{name: "hanako", age: 49},
		{name: "tomo", age: 37},
	]
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

</div>
