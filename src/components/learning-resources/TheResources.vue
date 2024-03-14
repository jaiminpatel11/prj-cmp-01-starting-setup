<template>
  <base-card>
    <base-button @click="setSelectedTab('stored-resources')"
    :mode="storeResourceButtonMode"
     >Stored Resourecs</base-button
    >
    <base-button @click="setSelectedTab('add-resources')"
    :mode="addResourcesButtonMode"
      >Add Resources</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import storedResources from './StoredResources';
import AddResources from './AddResources';

export default {
  components: {
    storedResources,
    AddResources,
  },
  data() {
    return {
      selectedTab: 'stored-resources',
      storedResources: [
        {
          id: 'official-guide',
          title: 'official guide',
          description: 'this is official documentation',
          link: 'https://vuejs.org',
        },

        {
          id: 'google',
          title: 'google=guide',
          description: 'this is official  google',
          link: 'https://google.com',
        },
      ],
    };
  },
  computed:{
       storeResourceButtonMode(){
        return this.selectedTab === 'stored-resources' ? null :'flat'
       },
       addResourcesButtonMode(){
        return this.selectedTab === 'add-resources' ? null :'flat'
       }
  },
  provide(){
    return{
        resources:this.storedResources
    }
  },

  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
};
</script>
