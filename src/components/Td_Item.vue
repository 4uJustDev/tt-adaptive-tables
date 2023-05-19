<template>
    <td><p class="text"><img src="@/icons/Groups.svg" alt="Group">{{row.id}}</p></td>
    <td><p class="text">{{row.name}}</p></td>
    <td><p class="text">{{row.price}}</p></td>
    
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