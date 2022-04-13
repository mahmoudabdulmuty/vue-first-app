<template>
  <section>
    <h2>Friend Contact</h2>
    <ul>
      <friend-contact></friend-contact>
      <friend-contact></friend-contact>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: 1,
          username: "Mahmoud Abdulmuty",
          phone: "4821 4874 541",
          email: "Mahmoud@example.com",
        },
        {
          id: 2,
          username: "Yusuf Saied",
          phone: "2482 487544 541",
          email: "Yusuf@example.com",
        },
        {
          id: 3,
          username: "Ahmed Salman",
          phone: "4821 7544 145",
          email: "Ahmed@example.com",
        },
      ],
    };
  },
};
</script>