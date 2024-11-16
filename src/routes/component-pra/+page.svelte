<script>
	import Child from '../../component/component-pra/child1/+page.svelte';
	import Books from '../../component/component-pra/books/+page.svelte';
	let props = '渡す'
</script>

<div>
	<h1>ああ</h1>
	<Child name='太郎'/>
	<Child />
	<Child name={props}/>
	<div class="mt-4">
		<ul>
			<Books/>
		</ul>
	</div>

</div>
