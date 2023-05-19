<template>
    <div class="table_adaptive">
        <div class="settings">
            <img src="@/icons/Settings.svg" alt="Settings">
        </div>
        <table id="resizeTable" class="table">
            <thead>
                <tr>
                <th v-for="head in headers" :key="headers.id">
                    <p class="text">{{head.name}}</p>
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
        },
        mounted(){
                // Query the table
                const table = document.getElementById('resizeTable');

                // Query all headers
                let cols = Array.from(table.querySelectorAll('th'));
                cols.pop();
                console.log(cols)

                cols.forEach(col=>{
                    // Create a resizer element
                    const resizer = document.createElement('div');
                    resizer.classList.add('resizer');

                    // Set the height
                    resizer.style.height = `${table.offsetHeight}px`;

                    // Add a resizer element to the column
                    col.appendChild(resizer);

                    // Will be implemented in the next section
                    this.createResizableColumn(col, resizer);
                });
        },
        methods:{
            createResizableColumn (col, resizer) {
                // Track the current position of mouse
                let x = 0;
                let  w = 0;

                const mouseDownHandler = function (e) {
                    // Get the current mouse position
                    x = e.clientX;

                    // Calculate the current width of column
                    const styles = window.getComputedStyle(col);
                    w = parseInt(styles.width, 10);

                    // Attach listeners for document's events
                    document.addEventListener('mousemove', mouseMoveHandler);
                    document.addEventListener('mouseup', mouseUpHandler);

                    resizer.classList.add('resizing');
                };

                const mouseMoveHandler = function (e) {
                    // Determine how far the mouse has been moved
                    const dx = e.clientX - x;

                    // Update the width of column
                    col.style.width = `${w + dx}px`;
                };

                // When user releases the mouse, remove the existing event listeners
                const mouseUpHandler = function () {
                    document.removeEventListener('mousemove', mouseMoveHandler);
                    document.removeEventListener('mouseup', mouseUpHandler);

                    resizer.classList.remove('resizing');
                };

                resizer.addEventListener('mousedown', mouseDownHandler);
            },
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
    .resizer {
        /* Displayed at the right side of column */
        position: absolute;
        top: 0;
        right: -0.5px;
        width: 5px;
        cursor: col-resize;
        user-select: none;
    }
    .resizer:hover,
    .resizing {
        border-right: 1px solid #eeeff1;
    }
    table tr th:first-child {
        border-left: none;
    }
    table tr th:last-child {
        border-right: none;
    }
    table th,
    table td{
        position: relative;
    }
</style>