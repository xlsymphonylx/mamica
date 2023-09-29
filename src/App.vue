<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="sidebar">
    <div class="sidebar__brand">
      ASONATCH
    </div>
    <ul class="sidebar__list">
      <RouterLink to="/" class="sidebar__link">Home</RouterLink>
    </ul>
  </div>

  <div class="content">
    <RouterView />
  </div>
</template>

<style scoped>
.sidebar {
  background-color: #cbd2e0;
  color: black;
  padding: 20px;
  width: 250px;
  height: 100%;
  position: fixed;
  top: 0;
  left: 0;
}

.sidebar__brand{
  font-size: 1.4rem;
  text-align: center;
}
.sidebar__list{
  padding-left: 0;
}
.sidebar__link {
  display: block;
  text-decoration: none;
  margin-bottom: 10px;
  text-align: center;
}

.content {
  margin-left: 250px;
  padding: 20px;
}
</style>
