<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
import { reactive } from 'vue'


const state = reactive({
    listItems: []
})
function fetchData() {
    fetch('http://localhost:3001/musicians').then(response => response.json()).then(data => {

        state.listItems.push(...data)

        console.log(state.listItems)

    })
};
fetchData()

</script>

<template>
    <nav class="nav">
        <!-- <h3>{{ title }}</h3> -->
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Sold Records</th>
                    <th>Foundation Date</th>
                    <th>Genre</th>
                </tr>
            </thead>
            <tr v-for="item in state.listItems" :key="item.first_name">
                <td>{{ item.first_name }}</td>
                <td>{{ item.sold_records }}</td>
                <td>{{ item.foundation_date }}</td>
                <td>{{ item.genre }}</td>
            </tr>
        </table>
        <button @click="fetchData()">Load More</button>
    </nav>
</template>
<style>
table {
    border: 1px solid white;
    padding: 30px;
}

tr:nth-child(even) {
    background-color: rgb(90, 92, 93);
}

td {
    padding: 10px;
}

th {
    padding: 10px;
    text-align: left;
}

button {
    margin-top: 40px;
    padding: 10px;
    font-size: 1em;
    color: white;
    background-color: grey;
    border: none;
    border-radius: 10px;
    cursor: pointer;
}

button:hover {
    background-color: white;
    color: black;
}
</style>
