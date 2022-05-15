<script>

</script>

<main>
	<img src="images/coming.gif" alt="j'arrive !"> <br />
	<img src="images/bean.png" class="bean" alt="Un petit haricot" /> <br />
	<h1>Bean arrive ! </h1>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
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
