<template>
    <div class="container">
        <h1>listado comunas</h1>
        <table class="table">
            <thead>
                <tr>
                    <th scope="col">#</th>
                    <th scope="col">Code</th>
                    <th scope="col">Name</th>
                    <th scope="col">Municipality</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(comuna, index) in comunas" :key="index">

                    <td scope="row">{{ index + 1 }}</td>
                    <td>{{ comuna.comu_codi }}</td>
                    <td>{{ comuna.comu_nomb }}</td>
                    <td>{{ comuna.muni_nomb }}</td>
                </tr>               
            </tbody>

        </table>


    </div>
</template>
<script>
import axios from 'axios'
export default {
    name: 'Comuna',
    data(){
        return{
        comunas: []
    }
},
mounted(){
    axios
    .get('http://127.0.0.1:8000/api/comunas')
    .then(response=>(this.comunas=response.data.comunas))
    console.log(this.comunas)
},
}
</script>
