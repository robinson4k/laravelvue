<template>
    <div>
        <h1>Listagem das categorias</h1>
        <router-link :to="{name: 'admin.categories.create'}" class="btn btn-success">Cadastrar</router-link>
        <table class="table table-dark">
            <thead>
                <th>ID</th>
                <th>NOME</th>
                <th>AÇÕES</th>
            </thead>
            <tbody>
                <tr v-for="(category, index) in categories.data" :key="index">
                    <td>{{ category.id }}</td>
                    <td v-text="category.name"></td>
                    <td>
                        <router-link :to="{name: 'admin.categories.edit', params: {id: category.id}}" class="btn btn-info">Editar</router-link>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
import axios from 'axios'

export default {
    created () {
        this.$store.dispatch('loadCategories')
    },
    computed: {
        categories () {
            return this.$store.state.categories.items
        }
    }
}
</script>
<style scoped>

</style>


