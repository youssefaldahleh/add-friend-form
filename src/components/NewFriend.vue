<template>
  <form action="" @submit.prevent>
    <div class="">
      <label for="">Name</label>
      <input type="text" v-model="enteredname"/>
    </div>
    <div class="">
      <label for="">Phone</label>
      <input type="text" v-model="enteredphone"/>
    </div>
    <div class="">
      <label for="">E-mail</label>
      <input type="text" v-model="enteredemail"/>
    </div>
    <button @click="addcontact">Add Friend</button>
  </form>
</template>
<script>
export default {
  data() {
    return {
      enteredname: "",
      enteredphone: "",
      enteredemail: "",
    };
  },
  methods: {
    addcontact() {
      this.$emit(
        "add-contact",
        this.enteredname,
        this.enteredphone,
        this.enteredemail
      );
    },
  },
};
</script>
