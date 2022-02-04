<template>
  <v-app style="background: #f4f4f5">
    
    <v-main>
      <NavBar />
      <Form />
      <Footer />
    </v-main>
  </v-app>
</template>

<script>
import NavBar from "./components/NavBar";
import Form from "./components/Form";
import Footer from "./components/Footer";

export default {
  name: "App",

  components: {
    NavBar,
    Form,
    Footer,
  },

  data: () => ({}),
};
</script>
<style>
html {
  overflow-y: auto !important;
}

.logo {
  width: 6em;
  height: 6em;
  animation: bounceIn 0.9s;
  transform: rotate(0deg) scale(1) translateZ(0);
  transition: all 0.4s cubic-bezier(0.8, 1.8, 0.75, 0.75);
  /* cursor: pointer; */
}
/*
.logo:hover {
  transform: rotate(-15deg) scale(1.1);
}
*/
.bubble {
  fill: #2c84cf;
}
.icon {
  fill: #fff;
}

.cls-1 {
  fill: #2c84cf;
}
.cls-2 {
  fill: #fefefe;
}

@keyframes bounceIn {
  0% {
    opacity: 1;
    transform: rotate(0deg) scale(0.1);
  }

  50% {
    opacity: 1;
    transform: rotate(-10deg) scale(1.2);
  }

  70% {
    opacity: 1;
    transform: rotate(-5deg) scale(0.75);
  }

  100% {
    opacity: 1;
    transform: rotate(0deg) scale(1);
  }
}
</style>