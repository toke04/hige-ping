<script>
	export let users = {};
</script>

<ul>
	{#each users as user}
		<li>名前: {user.name} 年齢: {user.age}</li>
	{/each}
</ul>
