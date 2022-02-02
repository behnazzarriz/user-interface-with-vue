<template>
<base-card>
  <base-button @click="selectTab('stored-resource')"
               :mode="storedResourcesButtonMod">
    Stored Resources
  </base-button>
  <base-button @click="selectTab('add-resources')"
               :mode="addResourceButtonMod">
    Add Resource
  </base-button>

  <component :is="selectedTab"></component>
</base-card>
</template>
<script>
import StoredResource from './StoredResources.vue';
import AddResources from './AddResources.vue';

export default {
  components: {
    StoredResource,
    AddResources
  },
  data(){
    return{
      selectedTab:'stored-resource',
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
  },
  computed:{
    storedResourcesButtonMod(){
     return  this.selectedTab==='stored-resource'?null:'flat';
    },
    addResourceButtonMod(){
      return this.selectedTab==='add-resources'?null:'flat';
    }
  },
  provide(){
  return{
    resources:this.storedResources
  }
  },
  methods:{
    selectTab(cmp){
      this.selectedTab=cmp;
    }
  }
}
</script>