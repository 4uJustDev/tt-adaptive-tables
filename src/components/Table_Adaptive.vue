<template>
    <div class="table_adaptive">
        <div class="settings">
            <img src="@/icons/Settings.svg" alt="Settings">
        </div>
        <table>
            <thead>
                <tr>
                <th v-for="head in headers" :key="headers.id">
                    {{head.name}}
                </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="row in rows" :key="row.id">
                    <Td_Item :row = "row"></Td_Item>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import Td_Item from '@/components/Td_Item.vue'
    export default {
        components:{
            Td_Item
        },
        data(){
            return{
                rows: [
                    { id: 1, name: "Chandler Bing", price: '1234'},
                    { id: 2, name: "Ross Geller", price: '1234'},
                    { id: 3, name: "Rachel Green", price: '1234'},
                    { id: 4, name: "Monica Geller", price: '1234'},
                    { id: 5, name: "Joey Tribbiani", price: '1234'},
                    { id: 6, name: "Phoebe Buffay", price: '1234'}
                ],
                headers:[
                    { id: 1, name: "Номер"},
                    { id: 2, name: "Наименование"},
                    { id: 3, name: "Цена"},
                ]
            }
    }
    }
</script>

<style>
    .table_adaptive{
        margin-top: 25px;
        padding: 0px 0px 25px 0px;
        border-radius: 10px;
        box-shadow: 0 5px 20px 0 rgba(0, 0, 0, 0.07);
        border: solid 1px #eeeff1;
        background-color: #fff;
        font-family: MyriadPro;
    }
    .settings{
        width: 100%;
        padding: 9px 15px 8px 0px;
        display: flex;
        justify-content: flex-end;
    }
    #firstTable{
        width: 100%;
    }
    table {
	width: 100%;
	margin-bottom: 20px;
	border-collapse: collapse; 
    }
    table th {
        font-weight: bold;
        padding: 5px;
        background: #fff;
        border: 1px solid #eeeff1;
    }
    table tr th:first-child {
        border-left: none;
    }
    table tr th:last-child {
        border-right: none;
    }
</style>