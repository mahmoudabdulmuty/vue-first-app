<template>
  <li>
    <h2>
      {{ username }}
      {{ isFavorite ? "(Favorite)" : "" }}
    </h2>
    <button @click="toggleVisible">
      {{ dataIsVisible ? "Hide" : "Show" }} Details
    </button>
    <button @click="toggleFavorite">Toggle Favorite</button>
    <ul v-if="dataIsVisible">
      <li>
        <strong>Phone:</strong>
        {{ phoneNumber }}
      </li>
      <li>
        <strong>Email:</strong>
        {{ email }}
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  props: {
    email: {
      type: String,
    },
    phoneNumber: {
      type: String,
    },
    username: {
      type: String,
    },
    isFavorite: {
      type: Boolean,
    },
    id: {
      type: Number,
    },
  },
  emits: {
    "toggle-favorite": function (id) {
      if (id) {
        return true;
      } else {
        console.warn("id is missing");
        return false;
      }
    },
  },
  data() {
    return {
      dataIsVisible: false,
      isFavoriteValue: this.isFavorite,
    };
  },
  methods: {
    toggleVisible() {
      this.dataIsVisible = !this.dataIsVisible;
    },
    toggleFavorite() {
      this.$emit("toggle-favorite", this.id);
    },
  },
};
</script>

<style scoped></style>
