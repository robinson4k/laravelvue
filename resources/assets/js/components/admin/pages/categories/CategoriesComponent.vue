<template>
    <div>
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
                    <td></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
import axios from 'axios'

export default {
    created () {
        this.loadCategories()
    },
    data () {
        return {
            categories: {
                data: []
            },
        }
    },
    methods: {
        loadCategories () {
            axios.get('/api/v1/categories')
            .then(response => {
                console.log(response)

                this.categories = response
            })
            .catch(errors => {
                console.log(errors)
            })
        }
    }
}
</script>
<style scoped>

</style>


