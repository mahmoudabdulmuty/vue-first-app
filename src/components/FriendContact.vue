<template>
  <li>
    <h2>{{ friend.username }}</h2>
    <button @click="toggleDetails">{{ detailsValue }} Details</button>
    <ul v-if="dataIsVisible">
      <li><strong>Phone : </strong> {{ friend.phone }}</li>
      <li><strong>Email : </strong> {{ friend.email }}</li>
    </ul>
  </li>
</template>


<script>
export default {
  data() {
    return {
      dataIsVisible: false,
      friend: {
        id: 1,
        username: "Mahmoud Abdulmuty",
        phone: "4821 4874 541",
        email: "Mahmoud@example.com",
      },
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