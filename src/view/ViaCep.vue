<template>
    <div>
        <h1>Consult CEP</h1>
        <form action="#" onsubmit="event.preventDefault()">
            <div class="form-floating mb-3">
                <input id="cep" v-model="cep" type="text" class="form-control" placeholder="Enter the CEP">
            </div>
            <input type="button" class="btn btn-primary" value="Search" @click="getCep">
        </form>
        <div>
            <h5>Street:</h5><p>{{ place.street }} </p>
            <h5>Neighborhood:</h5><p> {{ place.neighborhood }}</p>
            <h5>City:</h5><p>{{ place.city }}/{{ place.state }}</p>
        </div>
    </div>
</template>

<script setup>
import axios from 'axios'
import { reactive, ref } from 'vue'

const baseUrl = 'https://viacep.com.br/ws/'
const format = '/json'

const cep = ref("")

const place = reactive({
    street: '',
    neighborhood: '',
    city: '',
    state: ''
})

const getCep = () => {
    axios.get(baseUrl + cep.value + format)
        .then((response) => {
            console.log(response);
            place.street = response.data.logradouro,
                place.neighborhood = response.data.bairro,
                place.city = response.data.localidade,
                place.state = response.data.uf
        })
        .catch((error) => {
            console.log('Something went wrong!', error);
        })
}

</script>
<style scoped></style>