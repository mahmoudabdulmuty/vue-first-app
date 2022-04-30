<template>
  <form @submit.prevent="submit">
    <div>
      <label> Name: </label>
      <input type="text" placeholder="enter friend name" v-model="username" />
    </div>
    <div>
      <label> Email: </label>
      <input type="email" placeholder="enter friend email" v-model="email" />
    </div>
    <div>
      <label> Phone: </label>
      <input
        type="tel"
        placeholder="enter friend number"
        v-model="phoneNumber"
      />
    </div>
    <div>
      <button>Add Friend</button>
    </div>
  </form>
</template>


<script>
export default {
  data: function () {
    return {
      username: "",
      email: "",
      phoneNumber: "",
    };
  },
  emits: ["add-friend"],
  methods: {
    submit() {
      const newFriend = {
        name: this.username,
        email: this.email,
        phone: this.phoneNumber,
        id: Math.random(),
        isFavorite: false,
      };
      this.$emit("add-friend", newFriend);
    },
  },
};
</script>