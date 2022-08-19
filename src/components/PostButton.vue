<template>
    <div>
        <div>
            <button @click="post_message">POST</button>
        </div>
    </div>
</template>

<script>
    export default {
        methods: {
            post_message() {
                this.$root.$emit(`toast_notify`, `Successfully Posted.`);
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>