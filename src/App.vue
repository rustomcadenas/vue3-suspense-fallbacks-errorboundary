<template>
  <div>
    <div>
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-view />
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped lang="postcss">
  .router-link-active,
  .router-link-exact-active{
    @apply text-green-500
  }

</style>