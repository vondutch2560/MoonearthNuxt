<template>
  <div class="breadcrumb">
    <ul>
      <li><NuxtLink to="/">Home</NuxtLink></li>
      <li v-for="(item, index) in breadcrumb" :key="index">
        <NuxtLink :to="item.link">{{ item.name }}</NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    breadcrumb: { type: Array, default: () => [] }
  }
}
</script>

<style>
.breadcrumb {
  border-bottom: 2px solid #eee;
}

.breadcrumb ul {
  padding: 38px 0 12px 0;
}
.breadcrumb ul li {
  display: inline-block;
  color: #777;
}
.breadcrumb ul li a {
  display: inline-block;
  color: var(--main-color);
  padding: 2px 0;
}
.breadcrumb ul li:before {
  content: '\203A';
  display: inline-block;
  color: var(--main-color);
  padding: 0 9px 0 7px;
}
.breadcrumb ul li:first-child:before {
  content: none;
}
.breadcrumb ul li:last-child a {
  color: #777;
}
</style>
