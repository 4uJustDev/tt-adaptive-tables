<template>
    <select class="my_item">
        <option value="test">
            <slot class="text"></slot>
        </option>
    </select>
</template>

<script>
    export default {
        name: 'my-item',
    }
</script>

<style scoped>
.my_item{
    padding: 9px 0px 9px 15px;
    border-radius: 5px;
    border: solid 1px #ccc;
    width: 100%;
    
    appearance: none;
}
.text{
    size: 16px;
    height: 16px;
    font-family: 'MyriadPro';
    font-size: 16px;
    font-weight: normal;
}
</style>