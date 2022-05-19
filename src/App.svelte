<script>
import Background from './components/Background.svelte';

</script>

<main class="flex justify-center align-middle h-full">
	<Background />
	<div class="flex flex-col h-full">
		<div class="bubble relative">
			<span class="coming absolute text-xl font-mono"></span>
		</div>
		<img src="images/bean.png" class="bean absolute w-52 z-50" alt="Un petit haricot" />
	</div>
</main>

<style lang="postcss">
@tailwind base;
@tailwind components;
@tailwind utilities;

.bubble {
	background: url('/images/speech-bubble.png') no-repeat center center / 100% auto;
	width: 180px;
	height: 180px;
	z-index: 1000;
	top: 50%;
	right: 110px;
}

.coming {
	top: 68px;
	left: 32px;
}
.bean {
	bottom: 10px;
  animation: rotation 4s infinite ease;
	z-index: 1000;
}

@keyframes rotation {
	from {
		transform:rotate(0deg);
	}
	to {
		transform:rotate(360deg);
	}
}
</style>
