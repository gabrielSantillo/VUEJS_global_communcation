<template>
  <div>
    <button @click="get_all_users">GET THE USERS</button>
    <section ref="user_container" v-if="error_message !== undefined">{{error_message}}</section>
    </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
     users: [],
     error_message: undefined
    };
  },
  methods: {
    get_all_users() {
     axios.request({
        url: `https://fakeapi.com/allusers`
     }).then((response) => {
        this.users.push(`${response[`data`][`users`]}`)
     }).catch((error) => {
        this.error_message = error
     })
    },
  },
};
</script>