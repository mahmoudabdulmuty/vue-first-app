<template>
  <li>
    <h2>{{ username }}</h2>
    <button @click="toggleDetails">{{ detailsValue }} Details</button>
    <ul v-if="dataIsVisible">
      <li><strong>Phone : </strong> {{ phoneNumber }}</li>
      <li><strong>Email : </strong> {{ emailAddress }}</li>
    </ul>
  </li>
</template>


<script>
export default {
  props: ["username", "phoneNumber", "emailAddress"],
  data() {
    return {
      dataIsVisible: false,
    };
  },
  methods: {
    toggleDetails() {
      this.dataIsVisible = !this.dataIsVisible;
    },
  },
  computed: {
    detailsValue() {
      return this.dataIsVisible ? "Hide" : "Show";
    },
  },
};
</script>