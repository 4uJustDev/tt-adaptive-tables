<template>
    <div>
        <div class="btns_group">
            <my-button>Добавить строку</my-button>
        </div>
        <Table_Adaptive></Table_Adaptive>
    </div>
</template>

<script>
import Table_Adaptive from './Table_Adaptive.vue';

    export default {
    components: { Table_Adaptive }
}
</script>

<style scoped>  
    .btns_group{
        width: 100%;
        padding: 20px 25px;
        border-radius: 10px;
        box-shadow: 0 5px 20px 0 rgba(0, 0, 0, 0.07);
        border: solid 1px #eeeff1;
        background-color: #fff;
    }
    .btn{
        padding: 10px 15px 10px 10px;
        border: none;
        display: flex;
        align-items: center;
        border-radius: 5px;
        background-color: #2f8cff;
        
        font-family: MyriadPro;
        font-size: 14px;
        font-weight: normal;
        font-stretch: normal;
        font-style: normal;
        line-height: normal;
        letter-spacing: normal;
        color: #fff;
    }
    .image{
        margin-right: 7px;
    }
</style>