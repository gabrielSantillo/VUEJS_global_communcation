<template>
  <div>
    <div v-if="hide_message">
         <h2 ref="message"></h2>
    </div>
   
    <div v-if="dismiss_message">
      <button @click="dismiss_message_function" ref="dismiss_button">
        Dismiss Message
      </button>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    handle_delete(message) {
      this.$refs[`message`].insertAdjacentHTML(`beforeend`, `${message}`);

      this.dismiss_message = true;
    },

    dismiss_message_function() {
        this.hide_message = false;
        this.dismiss_message = false;
    }
    ,
  },

  mounted() {
    this.$root.$on(`toast_notify`, this.handle_delete);

  },

  data() {
    return {
      dismiss_message: false,
      hide_message: true
    };
  },
};
</script>

<style scoped></style>
