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
	<div class="flex flex-col flex-1 w-full h-full z-10">
		<h1 class="text-center mt-4 text-7xl font-indieflower text-white">Bean arrive bientôt !</h1>
		<div class="mt-auto mx-auto">
			<div class="bubble flex relative right-16">
				<span class="bubble__text absolute w-44 text-center text-2xl font-indieflower">
					J'arrive dans
					{ remaingingDays } jours 
					{ remaingingHours } heures 
					et { remaingingMinutes } minutes !
				</span>
			</div>
			<img src="images/bean.png" class="bean w-52 relative left-14 z-10" alt="Un petit haricot" />
		</div>
	</div>
</main>

<style lang="postcss">
@tailwind base;
@tailwind components;
@tailwind utilities;

.bubble {
	background: url('/images/speech-bubble.png') no-repeat center center / 100% auto;
	width: 232px;
	height: 232px;
}

.bubble__text {
	top: 50px;
	left: 25px;
}

.bean {
  animation: rotation 4s infinite ease;
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
