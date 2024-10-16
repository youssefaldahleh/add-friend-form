<template>
  <li>
    <h2>{{ name }} {{isFavorite  ? "(Fav)" : "" }}</h2>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Hide" : "Show" }} Details
    </button>
    <button @click="toggleFavrite">Favorite</button>
    <button @click="Delete">Delete</button>
    
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone:</strong>
        {{ phoneNumber }}
      </li>
      <li>
        <strong>Email:</strong>
        {{ emailAddress }}
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  props: ["id","name", "phoneNumber", "emailAddress", "isFavorite"],
  data() {
    return {
      detailsAreVisible: false,
   
      
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavrite(){
      this.$emit('tog-fav',this.id)
    },
    Delete(){
      this.$emit('del-friend',this.id)
    }


  },
};
</script>
