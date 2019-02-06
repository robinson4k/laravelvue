<template>
  <div>
    <ul class="nav nav-dark">
      <li class="nav-item">
        <router-link :to="{name: 'admin.dashboard'}" class="nav-link">Dashboard</router-link>
      </li>
      <li class="nav-item">
        <router-link :to="{name: 'admin.categories'}" class="nav-link">Categorias ({{totalCategories}})</router-link>
      </li>
      <li>
          <router-link :to="{name: 'admin.products'}" class="nav-link">Produtos</router-link>
      </li>
    </ul>
    <router-view></router-view>
  </div>
</template>
<script>
export default {
  computed: {
    totalCategories() {
      return this.$store.state.categories.items.data.length;
    }
  }
};
</script>
<style scoped>
</style>
