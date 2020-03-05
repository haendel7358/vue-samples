<template>
  <div>
    <Welcome :name="name" />    
    <button @click="changeName">Change name</button>
  </div>
</template>

<script>
import Welcome from "./components/Welcome.vue";
export default {
  data: function() {
    return {
      name: "Gowtham"    
      };
  },
  methods: {
    changeName() {
      this.name = "Vue";
    }
  },
  components: { Welcome }
};
</script>