<template>
    <div class="col">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "wxc-col",
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
    .col{
        flex-direction: column;
    }
</style>