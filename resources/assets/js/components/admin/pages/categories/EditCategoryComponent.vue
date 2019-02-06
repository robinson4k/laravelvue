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
        this.loadCategory()
    },
    data () {
        return {
            category: {
                name: ''
            }
        }
    },
    methods: {
        loadCategory () {
            this.$store.dispatch('loadCategory', this.id)
            .then(response => {
                this.category = response
                console.log(response)
            })
            .catch(error => {
                console.log(error)
                this.$snotify.error('Categoria não encontrada', '404')
                this.$router.push({name: 'admin.categories'})
            })
        }
    },
    components: {
        formCat: FormCategoryComponent
    }
}
</script>
<style scoped>
</style>