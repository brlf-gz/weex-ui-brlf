<template>
    <div class="row">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "wxc-row",
        props: {

        },
        data: function () {
            return {

            }
        },

        methods: {
        },
    }

</script>

<style scoped>
    .row{
        flex-direction: row;
    }
</style>