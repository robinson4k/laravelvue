<template>
    <div>
        <h1>Editar categoria</h1>
        <form-cat :category="category" :updating="true"></form-cat>
    </div>
</template>
<script>

import FormCategoryComponent from './partials/FormCategoryComponent'

export default {
    // VALORES QUE ELE ESPERA
    props: {
        id: {
            require: true
        }
    },
    // quando o componente é chamado, executa este metodo
    created () {
        this.$store.dispatch('loadCategory', this.id)
        .then(response => {
            this.category = response
            console.log(response)
        })
        .catch(error => {
            console.log(error)
        })
    },
    data () {
        return {
            category: {
                name: ''
            }
        }
    },
    components: {
        formCat: FormCategoryComponent
    }
}
</script>
<style scoped>
</style>