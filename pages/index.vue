<template>
  <div>
    <!-- HOME -->
    <div class="home bg-primary flex justify-center items-center flex-col">
      <h1 class="text-6xl text-white font-bold">Jack Driscoll</h1>
      <h6 class="text-xl text-white font-semibold">Web Developer</h6>
      <a
        href="#about"
        class="view-work mt-4 text-white border-white text-2xl p-3 border-white border-2 shadow-xl rounded-md focus:outline-none"
      >
        View My Work
      </a>
      <div class="wave wave1"></div>
      <div class="wave wave2"></div>
      <div class="wave wave3"></div>
      <div class="wave wave4"></div>
    </div>
    <div id="about" class="about flex">
      <div class="nav shadow-md h-16 min-w-full">
        <div
          class="nav-title self-start font-semibold text-xl p-4 text-primary"
        >
          Jack Driscoll
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    document.querySelectorAll('a[href^="#"]').forEach((anchor) => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault()

        document.querySelector(this.getAttribute('href')).scrollIntoView({
          behavior: 'smooth',
        })
      })
    })
  },
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
* {
  margin: 0;
  padding: 0;
}
.home {
  width: 100%;
  height: 100vh;
}

.view-work {
  transition: background-color 0.2s ease;
}
.view-work:hover {
  color: #3586ff;
  background-color: white;
}
.about {
  width: 100%;
  height: 100vh;
  background: white;
}
div .wave {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100px;
  background: url('/wave.png');
  background-size: 1000px 100px;
  z-index: 1000;
}
div .wave.wave1 {
  animation: animate 25s linear infinite;
  z-index: 4;
  opacity: 1;
  animation-delay: 0s;
  bottom: 0;
}
div .wave.wave2 {
  animation: animate 20s linear infinite;
  animation-direction: reverse;
  z-index: 3;
  opacity: 0.5;
  animation-delay: -5s;
  bottom: 10px;
}
div .wave.wave3 {
  animation: animate 10s linear infinite;
  z-index: 2;
  opacity: 0.2;
  animation-delay: -2s;
  bottom: 15px;
}
div .wave.wave4 {
  animation: animate 5s linear infinite;
  animation-direction: reverse;
  z-index: 1;
  opacity: 0.7;
  animation-delay: -5s;
  bottom: 20px;
}
@keyframes animate {
  0% {
    background-position-x: 0;
  }
  100% {
    background-position-x: 1000px;
  }
}
</style>
