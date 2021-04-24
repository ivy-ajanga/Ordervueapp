<template>
    <div class = "container">
    <h3>Orders:</h3>
        <table class="table">
            <thead>
                <tr>
                    <th scope="col">Id</th>
                    <th scope="col">orderNumber</th>
                    <th scope="col">count</th>
                    <th scope="col">created_at</th>
                    <th scope="col">updated_at</th>
                    <th scope="col">deleted_at</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="user in orders" v-bind:key="user.id">
                    <th scope="row">{{user.id}}</th>
                    <td>{{user.orderNumber}}</td>
                    <td>{{user.count}}</td>
                    <td>{{user.created_at}}</td>
                    <td>{{user.updated_at}}</td>
                    <td>{{user.deleted_at}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    import axios from 'axios';
    export default{
        name: 'Orders',
        data() {
            return {
              orders:null,  
            };
        },
        created: function(){
           axios
            .get ('https://codechallenge.pikdrive.com/api/orders')
            .then (res=> {
                this.orders = res.data;
            })
        }
    }
</script>
<style>
h3 {
    margin-bottom:5%;
}
</style>