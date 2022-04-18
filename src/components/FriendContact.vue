<template>
  <li>
    <h2>{{ username }} {{ isDataFavorite ? "(Favorite)" : "" }}</h2>
    <button @click="toggleDetails">{{ detailsValue }} Details</button>
    <button @click="toggleFavorite">toggle Favorite</button>
    <ul v-if="dataIsVisible">
      <li><strong>Phone : </strong> {{ phoneNumber }}</li>
      <li><strong>Email : </strong> {{ emailAddress }}</li>
    </ul>
  </li>
</template>


<script>
export default {
  props: {
    username: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: String,
      required: true,
    },
    emailAddress: {
      type: String,
      required: false,
      default: "mahmoudabdulmuty@gmail.com",
    },
    isFavorite: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
  data() {
    return {
      dataIsVisible: false,
      isDataFavorite: this.isFavorite,
    };
  },
  methods: {
    toggleDetails() {
      this.dataIsVisible = !this.dataIsVisible;
    },
    toggleFavorite() {
      this.isDataFavorite = !this.isDataFavorite;
    },
  },
  computed: {
    detailsValue() {
      return this.dataIsVisible ? "Hide" : "Show";
    },
  },
};
</script>