<template>
    <div class="table_adaptive">
        <table id="firstTable">
            <thead>
                <tr>
                <th>Номер</th>
                <th>Наименование</th>
                <th>Цена</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="row in rows" :key="row.id">
                <td><img src="@/icons/Groups.svg" alt="Group">{{row.id}}</td>
                <td>{{row.name}}</td>
                <td>{{row.price}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                rows: [
                    { id: 1, name: "Chandler Bing", price: '305-917-1301'},
                    { id: 2, name: "Ross Geller", price: '210-684-8953'},
                    { id: 3, name: "Rachel Green", price: '765-338-0312'},
                    { id: 4, name: "Monica Geller", price: '714-541-3336'},
                    { id: 5, name: "Joey Tribbiani", price: '972-297-6037'},
                    { id: 6, name: "Phoebe Buffay", price: '760-318-8376'}
                ]
            }
    }
    }
</script>

<style scoped>
    .table_adaptive{
        margin-top: 25px;
        padding: 32px 0px 25px 0px;
        border-radius: 10px;
        box-shadow: 0 5px 20px 0 rgba(0, 0, 0, 0.07);
        border: solid 1px #eeeff1;
        background-color: #fff;
    }
    table th {
    text-transform: uppercase;
    text-align: left;
    background: #44475C;
    color: #FFF;
    padding: 8px;
    min-width: 30px;
    }

    table td {
    text-align: left;
    padding: 8px;
    }
    table td:last-child {
    border-right: none;
    }
    table tbody tr:nth-child(2n) td {
    background: #D4D8F9;
    }
</style>