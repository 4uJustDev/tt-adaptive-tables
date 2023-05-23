<template>
    <button class="btn">
        <img src="@/icons/Plus.svg" alt="Add" class="image">
        <slot></slot>
    </button>
</template>

<script>
    export default {
        name: 'my-button',
    }
</script>

<style scoped>
    .btn{
        padding: 10px 15px 10px 10px;
        border: none;
        display: flex;
        align-items: center;
        border-radius: 5px;
        background-color: #2f8cff;
        font-family: 'MyriadPro';
        font-size: 14px;
        font-weight: normal;
        color: #fff;
    }
    .image{
        margin-right: 7px;
    }
</style>