<template>
    <div>
        <button @click="delete_function">DELETE</button>
    </div>
</template>

<script>
    export default {
        methods: {
            delete_function() {
                this.$root.$emit(`toast_notify`, `Successfully deleted.`);
            }
        },
        
    }
</script>

<style lang="scss" scoped>

</style>