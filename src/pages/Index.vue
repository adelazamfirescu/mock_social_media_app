<template>
  <q-page class="flex column q-pa-md">
    <UserCard v-for="user in userList" :key="user.id" :user="user" />
  </q-page>
</template>

<script>
import UserCard from "../components/UserCard.vue";

export default {
  name: "PageIndex",
  data() {
    return {
      userList: [],
    };
  },
  components: {
    UserCard,
  },
  mounted() {
    this.$axios
      .get("https://reqres.in/api/users")
      .then((res) => {
        this.userList = res.data.data;
        console.log(res.data);
      })
      .catch((err) => console.log(err));
  },
};
</script>

//-------script for composition API---------
// import { defineComponent } from "vue";
// import { onMounted } from "vue";
// import axios from "axios";
// import UserCard from "../components/UserCard.vue";

// export default defineComponent({
//   name: "PageIndex",
//   components: { UserCard },
//   data() {
//     return {
//       userList: [],
//     };
//   },
//   setup() {
//     onMounted(() => {
//       axios
//         .get("https://reqres.in/api/users")
//         .then((res) => {
//           this.userList = res.data;
//         })
//         .catch((err) => console.log(err));
//     });
//   },
// });


