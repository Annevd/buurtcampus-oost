<script>
	export let data;
	import { Navigation, AccessibilityMenu, Menu, Footer } from '$lib/index.js';
</script>

<Navigation />

<div class="train">
	<div class="engine-front">
		<div class="chimney">
		<div class="smoke"></div>
		<div class="smoke smoke-2"></div>
		<div class="smoke smoke-3"></div>
		<div class="smoke smoke-4"></div>
		</div>
	</div>

	<div class="engine-body"></div>

	<div class="compartment">
		<div class="compartment-window"></div>
	</div>

	<div class="compartment compartment-two">
		<div class="compartment-window"></div>
	</div>

	<div class="compartment compartment-three">
		<div class="compartment-window"></div>
	</div>

	<div class="wheel-holder">
		<div class="wheel"></div>
		<div class="wheel wheel-2">
		<div class="wheel-joint"></div>
		<div class="wheel-joint wheel-joint-2"></div>
		</div>
		<div class="wheel wheel-3"></div>
		<div class="wheel wheel-4"></div>
		<div class="wheel wheel-5"></div>
		<div class="wheel wheel-6"></div>
		<div class="wheel wheel-7"></div>
		<div class="wheel wheel-8"></div>
		<div class="wheel wheel-9"></div>
	</div>
</div>

<slot />
<Footer {data} />

<style>
	
.train {
  bottom: 0;
  height: 10rem;
  position: fixed;
  left: calc(100% + 1.3rem);
  width: 44rem;
  z-index: 100;

  @supports (animation-timeline: scroll()) {
	animation: move-train linear;
	animation-timeline: scroll(root y);
  }
}

.engine-front {
  background: linear-gradient(0deg, #191919, #262626, #191919);
  border: 0.1rem solid rgba(255, 255, 255, 0.15);
  border-radius: 0.5rem 0 0 0.5rem;
  border-right: none;
  animation: body-upDown 0.3s infinite;
  bottom: 1.4rem;
  height: 4.6rem;
  left: 0;
  position: absolute;
  width: 8rem;
}

.engine-front::before,
.engine-front::after {
  background: linear-gradient(0deg, #191919, #262626, #191919);
  border: 0.1rem solid rgba(255, 255, 255, 0.15);
  border-radius: 50% 0 0 50%;
  border-right: none;
  content: "";
  position: absolute;
  height: 70%;
  left: -0.9rem;
  top: 50%;
  transform: translate(0, -50%);
  width: 0.8rem;
}

.engine-front::after {
  height: 40%;
  left: -1.4rem;
  width: 0.5rem;
}

.chimney {
  background: #800000;
  height: 2.2rem;
  left: 2.5rem;
  position: absolute;
  top: -2.3rem;
  width: 1.7rem;
}

.chimney::before {
  animation: up-down 0.3s infinite;
  border-bottom: none;
  border-left: 0.5rem solid transparent;
  border-right: 0.5rem solid transparent;
  border-top: 0.8rem solid orange;
  content: "";
  left: 50%;
  position: absolute;
  top: -0.9rem;
  transform: translate(-50%, 0);
  width: 160%;
}

.smoke {
  animation: move-smoke 0.4s linear infinite;
  background: rgba(255, 255, 255, 0.8);
  border-radius: 50%;
  height: 1.4rem;
  left: 0.2rem;
  position: absolute;
  top: -1.5rem;
  width: 0.8rem;
  z-index: -1;
}

.smoke-2 {
  animation-delay: 0.1s;
  left: 0.4rem;
}

.smoke-3 {
  animation-delay: 0.2s;
  left: 0.6rem;
}

.smoke-4 {
  left: 0.8rem;
}

.engine-body {
  animation: body-upDown 0.3s 0.1s infinite;
  background: linear-gradient(0deg, #8b0000, red, #800000);
  border-radius: 0 0 0.4rem 0;
  bottom: 1.4rem;
  height: 7rem;
  left: 8rem;
  position: absolute;
  width: 5rem;
}

.engine-body::before {
  animation: up-down 0.3s 0.2s infinite;
  background: linear-gradient(0deg, #640000, #800000, #640000);
  border-radius: 50% 50% 0 0;
  content: "";
  height: 1.2rem;
  left: 50%;
  position: absolute;
  top: -1.2rem;
  transform: translate(-50%, 0);
  width: 130%;
}

.engine-body::after {
  background: #8fceff;
  border-radius: 0.2rem;
  content: "";
  height: 40%;
  left: 50%;
  position: absolute;
  top: 1rem;
  transform: translate(-50%, 0);
  width: 45%;
}

.wheel-holder {
  height: 2.8rem;
  bottom: 0;
  position: absolute;
  width: 100%;
}

.wheel {
  animation: rotate 2s linear infinite;
  background: orange;
  border: 0.3rem solid rgba(0, 0, 0, 0.6);
  border-radius: 50%;
  height: 2.8rem;
  left: 1rem;
  position: absolute;
  width: 2.8rem;
}

.wheel-2 {
  left: 4.5rem;
  z-index: 1;
}

.wheel-3 {
  border-width: 0.5rem;
  height: 3.8rem;
  left: 8.7rem;
  top: -1.1rem;
  width: 3.8rem;
}

.wheel-4 {
  left: 15.7rem;
}

.wheel-5 {
  left: 19.5rem;
}

.wheel-6 {
  left: 25.7rem;
}

.wheel-7 {
  left: 29.5rem;
}

.wheel-8 {
  left: 35.7rem;
}

.wheel-9 {
  left: 39.5rem;
}

.wheel::before {
  background: rgba(0, 0, 0, 0.3);
  content: "";
  height: 86%;
  left: 50%;
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 0.2rem;
}

.wheel::after {
  background: radial-gradient(circle at center, #e67e00 30%, #cc6600 30%);
  border-radius: 50%;
  content: "";
  height: 40%;
  left: 50%;
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 40%;
}

.compartment {
  animation: body-upDown 0.3s infinite;
  background: linear-gradient(0deg, #8b0000, red, #800000);;
  border-radius: 0 0 0.3rem 0.3rem;
  bottom: 1.4rem;
  height: 5rem;
  left: 15rem;
  position: absolute;
  width: 8rem;
}

.compartment-two {
  animation: body-upDown 0.3s 0.1s infinite;
  left: 25rem;
}

.compartment-two .compartment-window::before {
  animation: up-down 0.3s 0.3s infinite;
}

.compartment-three {
  animation: body-upDown 0.3s 0.2s infinite;
  left: 35rem;
}

.compartment-three .compartment-window::before {
  animation: up-down 0.35s infinite;
}

.compartment::before,
.compartment::after {
  background: black;
  border: 0.4rem solid transparent;
  bottom: 0.4rem;
  box-shadow: 0 0 0 1px rgba(255, 255, 255, 0.1);
  content: "";
  height: 0.8rem;
  position: absolute;
  width: 0.9rem;
}

.compartment::before {
  border-left: 0.4rem solid rgba(255, 255, 255, 0.3);
  left: -0.9rem;
}

.compartment::after {
  border-right: 0.4rem solid rgba(255, 255, 255, 0.3);
  left: -2rem;
}

.compartment-window {
  background: linear-gradient(90deg, transparent 0.8rem, skyblue 0.8rem) left/2.4rem 100%;
  height: 40%;
  position: absolute;
  top: 0.7rem;
  width: 100%;
}

.compartment-window::before {
  animation: up-down 0.3s 0.1s infinite;
  background: #8b0000;
  border-radius: 50% 50% 0 0;
  content: "";
  height: 0.6rem;
  left: 50%;
  position: absolute;
  top: -1.4rem;
  transform: translate(-50%, 0);
  width: 110%;
}

@keyframes up-down {
  0%,
  100% {
    transform: translate(-50%, 0);
  }

  50% {
    transform: translate(-50%, -0.3rem);
  }
}

@keyframes rotate {
  100% {
    transform: rotate(-360deg);
  }
}

@keyframes body-upDown {
  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-2px);
  }
}

@keyframes move-smoke {
  0% {
    filter: blur(0);
    opacity: 1;
  }

  50% {
    filter: blur(0.2rem);
    opacity: 0.6;
    transform: translate(0, -3rem) scale(2);
  }

  100% {
    filter: blur(0.3rem);
    opacity: 0;
    transform: translate(2.5rem, -6rem) scale(3);
  }
}

.wheel-joint {
  animation: wheel-joint 2s linear infinite;
  background: white;
  border-radius: 0.6rem;
  height: 0.4rem;
  position: absolute;
  right: 0.4rem;
  top: calc(50% - 0.2rem);
  transform-origin: 100% 50%;
  width: 3.6rem;
  z-index: 1;
}

.wheel-joint::before {
  background: #333333;
  border: 0.1rem solid white;
  border-radius: 50%;
  content: "";
  height: 0.8rem;
  position: absolute;
  top: 50%;
  transform: translate(0, -50%);
  width: 0.8rem;
  left: -0.4rem;
}

.wheel-joint::after {
  background: #333333;
  border: 0.1rem solid white;
  border-radius: 50%;
  content: "";
  height: 0.8rem;
  position: absolute;
  top: 50%;
  transform: translate(0, -50%);
  width: 0.8rem;
  right: -0.4rem;
}

.wheel-joint-2 {
  left: 1.8rem;
  right: auto;
  transform: rotate(-15deg);
  transform-origin: 0 50%;
  width: 4.4rem;
}

.wheel-joint-2::before {
  height: 1.1rem;
  width: 1.1rem;
}

@keyframes wheel-joint {
  100% {
    transform: rotate(360deg);
  }
}

</style>