<template>
    <div>
        <h1>Cadastrar categoria</h1>
        <form-cat></form-cat>
    </div>
</template>
<script>

import FormCategoryComponent from './partials/FormCategoryComponent'

export default {
    components: {
        formCat: FormCategoryComponent
    }
}
</script>
<style scoped>
</style>