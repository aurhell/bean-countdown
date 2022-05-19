<script>
import Countdown from 'svelte-countdown/src/index.js'

import Background from './components/Background.svelte'
</script>

<main class="flex justify-center align-middle h-full">
	<Background />
	<div class="flex flex-col h-full">
		<h1 class="title absolute text-center mt-4 text-7xl font-indieflower text-white">Bean arrive bientôt !</h1>
		<div class="bubble relative">
			<span class="coming absolute text-lg font-indieflower">
				<Countdown from="2022-07-02 08:30:00" dateFormat="YYYY-MM-DD H:m:s" zone="Europe/Paris" let:remaining>
					{#if remaining.done === false}
					J'arrive dans
					<span>{remaining.weeks} semaines</span>
					<span>{remaining.days} jours</span>
					<span>{remaining.hours} heures</span>
					<span>et {remaining.minutes} minutes !</span>
					{:else}
					<h2>Je compte...</h2>
					{/if}
			</Countdown>
			</span>
		</div>
		<img src="images/bean.png" class="bean absolute w-52 z-50" alt="Un petit haricot" />
	</div>
</main>

<style lang="postcss">
@tailwind base;
@tailwind components;
@tailwind utilities;

@font-face {
  font-family: 'IndieFlower';
  src: url('../public/fonts/IndieFlower-Regular.ttf') format('truetype');
}

.title {
	left: 28%;
	z-index: 1000;
}
.bubble {
	background: url('/images/speech-bubble.png') no-repeat center center / 100% auto;
	width: 256px;
	height: 256px;
	z-index: 1000;
	top: 44%;
	right: 110px;
}

.coming {
	width: 200px;
	top: 66px;
	left: 32px;
}
.bean {
	bottom: 10px;
  animation: rotation 4s infinite ease;
	z-index: 1000;
}

@media screen and (max-device-width: 480px) {
	.title {
		left: 0;
	}

	.bubble {
		top: 32%;
    right: 58px;
	}

	.bean {
		left: 130px;
	}
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
