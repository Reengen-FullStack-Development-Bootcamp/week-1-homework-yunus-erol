<template>
    <nav class="nav-bar">
      <div class="container">
        <div class="brand">NIKE</div>
        <div class="basket">
          <b-dropdown size="lg"  variant="link" toggle-class="text-decoration-none" no-caret>
            <template #button-content>
              <i class="fas fa-shopping-basket"></i>
              <b-badge  variant="light">{{basket.lenght}}</b-badge>
          </template>
            <b-dropdown-item v-for="items in basket" :key="items">{{items}}</b-dropdown-item>
            <b-dropdown-item href="#">Another action</b-dropdown-item>
            <b-dropdown-item href="#">Something else here...</b-dropdown-item>
          </b-dropdown>
        </div>
      </div>
    </nav>
</template>

<script>

export default {
  name: 'Header',
  props : {
    basket: Array,
  }
}
</script>


<style scoped>
nav{
  background-color: #f6f4f5;
  width: auto;
  height: 50px;
  box-shadow: 1px 1px 3px rgba(112, 128, 144, 0.61);
  
}
.brand{
color: rgb(36, 36, 36);
}
.container{
  display: flex;
  box-sizing: border-box;
  justify-content:space-between;
  align-items: center;
 }
 .fas{
   color: rgb(36, 36, 36);
 }
</style>
