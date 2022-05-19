<div class="absolute w-full h-full">
  <div class="layer--0 absolute w-full h-full"></div>
  <div class="layer--1 absolute w-full h-full"></div>
  <div class="layer--2 absolute w-full h-full"></div>
  <div class="layer--3 absolute w-full h-full"></div>
  <div class="layer--4 absolute w-full h-full"></div>
  <div class="layer--5 absolute w-full h-full"></div>
  <div class="layer--6 absolute w-full h-full"></div>
  <div class="layer--7 absolute w-full h-full"></div>
</div>

<style lang="postcss">
  @tailwind base;
  @tailwind components;
  @tailwind utilities;

  @keyframes animatedBackground {
  from {
    background-position: 0 0;
  }
/*use negative width if you want it to flow right to left else and positive for left to right*/
  to {
    background-position: -10000px 0;
  }
}

.layer--0 {
	content: "";
	background: url('../images/background/layer-0.png');
	z-index: 81;

	background-repeat: repeat;
  background-position: 0 0;
  background-size: auto 100%;
  animation: animatedBackground 60s linear infinite;
}
.layer--1 {
	content: "";
	background: url('../images/background/layer-1.png');
	z-index: 70;

	background-repeat: repeat;
  background-position: 0 0;
  background-size: auto 100%;
  animation: animatedBackground 120s linear infinite;
}

.layer--2 {
	content: "";
	background: url('../images/background/layer-2.png');
	z-index: 60;

	background-repeat: repeat;
  background-position: 0 0;
  background-size: auto 100%;
  animation: animatedBackground 60s linear infinite;
}

.layer--3 {
	content: "";
	background: url('../images/background/layer-3.png');
	z-index: 50;

	background-repeat: repeat;
  background-position: 0 0;
  background-size: auto 100%;
  animation: animatedBackground 60s linear infinite;
}

.layer--4 {
	content: "";
	background: url('../images/background/layer-4.png');
	z-index: 40;

	background-repeat: repeat;
  background-position: 0 0;
  background-size: auto 100%;
  animation: animatedBackground 60s linear infinite;
}

.layer--5 {
	content: "";
	background: url('../images/background/layer-5.png');
	z-index: 30;

	background-repeat: repeat;
  background-position: 0 0;
  background-size: auto 100%;
  animation: animatedBackground 120s linear infinite;
}

.layer--6 {
	content: "";
	background: url('../images/background/layer-6.png');
	z-index: 20;

	background-repeat: repeat;
  background-position: 0 0;
  background-size: auto 100%;
  animation: animatedBackground 140s linear infinite;
}

.layer--7 {
	content: "";
	background: url('../images/background/layer-7.png');
	z-index: 10;

	background-repeat: repeat;
  background-position: 0 0;
  background-size: auto 100%;
  animation: animatedBackground 180s linear infinite;
}
</style>
