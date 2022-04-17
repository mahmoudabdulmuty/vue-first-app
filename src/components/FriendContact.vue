<template>
  <li>
    <h2>{{ username }} {{ isDataFavorite === "1" ? "(Favorite)" : "" }}</h2>
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
  // props: ["username", "phoneNumber", "emailAddress", "isFavorite"],
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
      default: 'mahmoudabdulmuty@gmail.com'
    },
    isFavorite: {
      type: String,
      required: false,
      default: "0",
      validator: function (value) {
        return value === "1" || value === "0";
      },
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
      if (this.isDataFavorite === "1") {
        this.isDataFavorite = "0";
      } else {
        this.isDataFavorite = "1";
      }
    },
  },
  computed: {
    detailsValue() {
      return this.dataIsVisible ? "Hide" : "Show";
    },
  },
};
</script>