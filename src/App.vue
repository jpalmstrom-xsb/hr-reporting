<template>
  <v-app style="background: #f4f4f5">

    <v-main>
      <Form/>
      <Footer />
    </v-main>
  </v-app>
</template>

<script>
import Form from './components/Form';
import Footer from './components/Footer';

export default {
  name: 'App',
  
  components: {
    Form,
    Footer
  },
  
  data: () => ({
    
  }),
};
</script>
<style>
html {
  overflow-y: auto !important;
}
</style>