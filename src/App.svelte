<script>
import Background from './components/Background.svelte'

let timeinterval = null
let remaingingDays = null
let remaingingHours = null
let remaingingMinutes = null

function getTimeRemaining(endtime) {
  const total = Date.parse(endtime) - Date.parse(new Date())
  const seconds = Math.floor((total / 1000) % 60)
  const minutes = Math.floor((total / 1000 / 60) % 60)
  const hours = Math.floor((total / (1000 * 60 * 60)) % 24)
  const days = Math.floor(total / (1000 * 60 * 60 * 24))

  return {
    total,
    days,
    hours,
    minutes,
    seconds
  }
}

function updateClock() {
  const t = getTimeRemaining('2022/07/02')
	
  if (t.total <= 0) {
    clearInterval(timeinterval)
  } else {
		remaingingDays = t.days
		remaingingHours = t.hours
		remaingingMinutes = t.minutes
	}
}

updateClock()
timeinterval = setInterval(updateClock, 1000)
</script>

<main class="flex justify-center align-middle h-full">
	<Background />
	<div class="flex flex-col h-full">
		<h1 class="title absolute text-center mt-4 text-7xl font-indieflower text-white">Bean arrive bientôt !</h1>
		<div class="bubble relative">
			<div id="clock" class="coming absolute text-lg font-indieflower">
				J'arrive dans
				{ remaingingDays } jours 
				{ remaingingHours } heures 
				et { remaingingMinutes } minutes !
		</div>
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
  src: url('/fonts/IndieFlower-Regular.ttf') format('truetype');
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
	top: 38%;
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
