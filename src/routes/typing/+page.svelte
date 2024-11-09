<script>
	import { writable } from "svelte/store";
	let input = '';
	let markIndex = 0;
	let finishWord = writable('');
	let questions = [
		{jp: 'たーだー', en: 'ta-da-'},
		{jp: 'いま', en: 'ima'},
		{jp: 'のかわりに', en: 'nokawarini'},
		{jp: '扉の音ー', en: 'tobiranooto-', showImage: true},
		{jp: 'を殺してー', en: 'wokoroshite-'},
		{jp: 'くらーいー', en: 'kura-i-',showImage: true},
		{jp: 'へーやへと', en: 'he-yaheto'},
		{jp: '抜きあーし', en: 'nukia-shi'},
		{jp: '差し足で-', en: 'sashiashide-',showImage: true},
		{jp: '入り込んで', en: 'hairikonde'},
		{jp: '眠るー', en: 'nemuru-'},
		{jp: '日々の先にー', en: 'hibinosakini-',showImage: true},
	];
	let currentIndex = 0;
	let question = questions[currentIndex];
	let images = [
		'https://ogre.natalie.mu/media/news/music/2024/1031/MV_SameBlue_making.jpg?imwidth=750&imdensity=1',
		'https://ogre.natalie.mu/media/news/music/2024/1028/GTE01102037.jpg?imwidth=750&imdensity=1',
		'https://ogre.natalie.mu/media/news/music/2023/0809/higedan_art202308.jpg?impolicy=thumb_fit&width=220&height=220',
		'https://ogre.natalie.mu/media/news/music/2023/0309/GD_higedan_JK_mixnuts.jpg?impolicy=thumb_fit&width=220&height=220',
		'https://ogre.natalie.mu/media/news/music/2022/0829/higedan_jkt202210cd.jpg?impolicy=thumb_fit&width=220&height=220',
	  'https://ogre.natalie.mu/media/news/music/2020/0409/officialhigedandism_art202004.jpg?impolicy=thumb_fit&width=220&height=220',
		'https://ogre.natalie.mu/media/news/music/2021/0129/officialhigedandism_jkt202102_dvd.jpg?impolicy=thumb_fit&width=220&height=220'
	]

	const changeQuestion = () => {
		question = questions[currentIndex];
	};

	const handleKeydown = (e) => {
		if (e.key === question.en[markIndex]) {
			markIndex++;
			input += e.key;
			if (markIndex === question.en.length) {
				finishWord = '正解！';
				markIndex = 0;
				currentIndex++;
				changeQuestion();
			}
		}
	};
</script>
<svelte:window on:keydown={handleKeydown} />
<svelte:head>
	<title>typing</title>
	<meta name="description" content="typing this app" />
</svelte:head>

<div>
	<h1 class="mb-16">ひげだんの<a href="https://www.youtube.com/watch?v=Ssj-NhrKOdg&ab_channel=Official%E9%AB%AD%E7%94%B7dism" target="_blank" rel="noopener noreferrer">Sharon</a>でタイピング！</h1>
	<h1>
		{#each question.jp.split('') as q}
			<span>{q}</span>
		{/each}
	</h1>
	<h1>
		{#each question.en.split('') as q,i}
			<span class={i === markIndex ? 'text-red-900' : '' }>{q}</span>
		{/each}
	</h1>
	{#if question.isLast}
		<h1>お疲れ様です！</h1>
	{/if}
	{#if question.showImage}
		<div style="display: flex; justify-content: center;">
			<img src={ images[Math.floor(Math.random() * images.length)] } alt="image" style="width: 300px; height: 300px;" />
		</div>
	{/if}
</div>
