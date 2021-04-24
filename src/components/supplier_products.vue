<template>
    <div class = "container">
    <h3>supplier_products:</h3>
        <table class="table">
            <thead>
                <tr>
                    <th scope="col">Id</th>
                    <th scope="col">supply_id</th>
                    <th scope="col">product_id</th>
                    <th scope="col">created_at</th>
                    <th scope="col">updated_at</th>
                    <th scope="col">deleted_at</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="user in supplier_products" v-bind:key="user.id">
                    <th scope="row">{{user.id}}</th>
                    <td>{{user.supply_id}}</td>
                    <td>{{user.product_id}}</td>
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
        name: 'supplier_products',
        data() {
            return {
              supplier_products:null,  
            };
        },
        created: function(){
           axios
            .get ('https://codechallenge.pikdrive.com/api/product-suppliers')
            .then (res=> {
                this.supplier_products = res.data;
            })
        }
    }
</script>
<style>
h3 {
    margin-bottom:5%;
}
</style>