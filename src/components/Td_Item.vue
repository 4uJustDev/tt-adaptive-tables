<template>
    <td><img src="@/icons/Groups.svg" alt="Group">{{row.id}}</td>
    <td>{{row.name}}</td>
    <td>{{row.price}}</td>
</template>

<script>
    export default {
        props: {
        row: {
            type: Object,
            required: true
        }
    },
    }
</script>

<style scoped>
    td {
        border: none;
        padding: 5px 10.5px;
    }
</style>