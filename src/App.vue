<template>
<the-header :title="headerTitle"></the-header>
 <stored-resource :resources="storedResources">

 </stored-resource>
</template>
<script>
import StoredResource from './components/learning-resources/StoredResources.vue';
import TheHeader from "./components/layouts/TheHeader.vue";

export default {
  components:{
   StoredResource,TheHeader
  },
  data(){
    return{
      headerTitle:'Remember Me',
      storedResources:[
        {
          id:'official-guide',
          title:'official Guide',
          description:'The official Vue.js documentation',
          link:'https://vuejs.org'
        },
        {
          id:'official-google',
          title:'google Guide',
          description:'The official google documentation',
          link:'https://google.org'


        }
      ]

    }
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>