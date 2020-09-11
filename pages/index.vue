<template>
  <div>
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"
    />
    <!-- HOME -->
    <div
      id="home"
      class="home bg-primary flex justify-center items-center flex-col"
    >
      <h1 class="text-6xl text-white font-bold">Jack Driscoll</h1>
      <h6 class="text-xl text-white font-semibold">Web Developer</h6>
      <a
        href="#about"
        class="view-work mt-4 text-white border-white text-2xl p-3 border-white border-2 shadow-xl rounded-md focus:outline-none"
      >
        About me
      </a>
      <div class="wave wave1"></div>
      <div class="wave wave2"></div>
      <div class="wave wave3"></div>
      <div class="wave wave4"></div>
    </div>
    <div class="nav shadow-md min-w-full flex-row sm:flex-col">
      <a
        href="#home"
        class="nav-title block sm:inline-block self-start font-semibold text-xl self-center text-primary"
      >
        Jack Driscoll
      </a>
      <div id="myLinks" class="hidden sm:inline-block">
        <a class="block sm:inline-block" href="#work">My Work</a>
        <a class="block sm:inline-block" href="#contact">Contact</a>
        <a class="block sm:inline-block" href="#about">About</a>
      </div>
      <a href="javascript:void(0);" class="icon" @click="showDropDown">
        <i class="fa fa-bars"></i>
      </a>
    </div>
    <div class="content h-screen">
      <div id="about" class="about flex flex-col bg-white min-w-full">
        <div class="heading h-24 sm:h-32 mt-12 flex w-1/2 mx-auto">
          <h1
            class="text-3xl md:text-5xl font-semibold text-primary self-center mx-auto"
          >
            About Me
          </h1>
        </div>
        <div class="flex flex-col bg-primary sm:flex-row sm:justify-around">
          <div class="md:w-4/12 w-full flex text-center py-12">
            <p class="text-white font-bold px-12">
              Hi, my name is Jack and I am an aspiring web developer.
              <br /><br />
              I may not have much here now, but I sure will soon.
              <br />
              <br />Give me a chance and I promise your project will be done to
              the level of a top tier professional.
            </p>
          </div>
          <div class="md:w-4/12 w-full bg-primary flex flex-col py-5">
            <h1 class="text-xl text-white font-bold mx-auto pb-5">
              Convinced already?
            </h1>
            <form>
              <div class="form-group flex justify-evenly my-2">
                <label class="text-white font-bold text-xl">Name</label>
                <input class="rounded-lg w-1/2" />
              </div>
              <div class="form-group flex justify-evenly my-2">
                <label class="text-white font-bold text-xl">Email</label>
                <input class="rounded-lg w-1/2" />
              </div>
              <div class="form-group flex justify-evenly my-2">
                <label class="text-white font-bold text-xl">Topic</label>
                <select class="rounded-lg w-1/2">
                  <option>Website Design</option>
                  <option>Web / Mobile Application</option>
                  <option>Design System</option>
                  <option>Other</option>
                </select>
              </div>
              <div class="form-group flex justify-evenly my-4">
                <button
                  class="bg-white text-primary font-bold border-1-primary w-1/2 p-5 rounded-full"
                >
                  Request me!
                </button>
              </div>
            </form>
          </div>
        </div>
      </div>
      <div
        id="work"
        class="work flex flex-col justify-evenly sm:flex-row min-w-full"
      >
        <div
          class="card w-full sm:w-4/12 flex flex-rol sm:flex-row m-1 h-full border-primary border-2 rounded-lg"
        >
          <div class="card-title w-full text-center">
            <h1 class="text-2xl font-extrabold text-primary">Work</h1>
          </div>
        </div>
        <div
          class="card w-full sm:w-4/12 flex flex-rol sm:flex-row m-1 h-full border-primary border-2 rounded-lg"
        >
          <div class="card-title w-full text-center">
            <h1 class="text-2xl font-extrabold text-primary">Projects</h1>
          </div>
        </div>
        <div
          class="card w-full sm:w-4/12 flex flex-rol sm:flex-row m-1 h-full border-primary border-2 rounded-lg"
        >
          <div class="card-title w-full text-center">
            <h1 class="text-2xl font-extrabold text-primary">Education</h1>
          </div>
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
  methods: {
    showDropDown() {
      const x = document.getElementById('myLinks')
      if (x.style.display === 'block') {
        x.style.display = 'none'
      } else {
        x.style.display = 'block'
      }
    },
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
.nav {
  position: sticky;
  top: 0;
  z-index: 1;
  background: white;
}
.nav a.icon {
  display: block;
  position: absolute;
  right: 0;
  top: 0;
}
.nav a {
  color: #3586ff;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}
.nav a:hover {
  background-color: #3586ff;
  color: white;
}
.active {
  background-color: #3586ff;
  color: white;
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
  animation: animate 15s linear infinite;
  z-index: 2;
  opacity: 0.2;
  animation-delay: -2s;
  bottom: 15px;
}
div .wave.wave4 {
  animation: animate 10s linear infinite;
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
