<template>
    <div class = "container">
    <h3>Products:</h3>
        <table class="table">
            <thead>
                <tr>
                    <th scope="col">Id</th>
                    <th scope="col">Name</th>
                    <th scope="col">Description</th>
                    <th scope="col">Quantity</th>
                    <th scope="col">created_at</th>
                    <th scope="col">updated_at</th>
                    <th scope="col">deleted_at</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="user in products" v-bind:key="user.id">
                    <th scope="row">{{user.id}}</th>
                    <td>{{user.name}}</td>
                    <td>{{user.description}}</td>
                    <td>{{user.quantity}}</td>
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
        name: 'Products',
        data() {
            return {
              products:null,  
            };
        },
        created: function(){
           axios
            .get ('https://codechallenge.pikdrive.com/api/products')
            .then (res=> {
                this.products = res.data;
            })
        }
    }
</script>
<style>
h3 {
    margin-bottom:5%;
}
</style>