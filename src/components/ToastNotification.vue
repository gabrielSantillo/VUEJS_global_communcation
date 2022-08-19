<template>
  <div v-if="notifications.length > 0">
    <div v-for="(notification, index) in notifications" :key="index">
         <h3>{{ notification }}</h3>
         <button @click="dismiss_message_function(index, $event)">
        Dismiss Message
      </button>
    </div>
   
    <div v-if="dismiss_message">
      
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            notifications: []
        }
    },
  methods: {
    notify_user(message) {
      if(this.notifications.length >= 3){
        this.notifications.splice(0,1)
      }
      this.notifications.push(message)
    },

    dismiss_message_function(index) {
        this.notifications.splice(index, 1)
    }
    ,
  },

  mounted() {
    this.$root.$on(`toast_notify`, this.notify_user);
  },

};
</script>

<style scoped></style>
