<template>
  <div>
    <div class="flex row q-my-md items-center user-card">
      <q-avatar size="80px">
        <img :src="user.avatar" />
      </q-avatar>
      <div class="q-ml-md">
        <p class="text-h6 text-weight-medium">{{ userFullName }}</p>
        <p class="text-overline text-weight-light">{{ user.email }}</p>
      </div>
    </div>
    <q-separator color="accent" />
  </div>
</template>

<script>
// import { defineComponent } from "vue";
// import { onMounted } from "vue";

export default {
  name: "UserCard",
  props: {
    user: Object,
  },
  mounted() {
    console.log(this.user);
  },
  computed: {
    userFullName() {
      return this.user.first_name + " " + this.user.last_name;
    },
  },
};
</script>

<style scoped>
.user-card {
}
.user-card p {
  margin-bottom: 0;
}
</style>