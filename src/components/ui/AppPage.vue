<template>
  <div class="breadcrumbs" v-if="back">
    <router-link class="text-white" to="/">Вернуться на главную страницу</router-link>
  </div>
  <div class="card">
        <h1 class="card-title">
          {{ title }}
          <slot name="header"></slot>
        </h1>

      <slot></slot>
  </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            required: true
        },
        back: {
          type: Boolean,
          default: false
        }
    },
    setup(props) {
        document.title = `${props.title} | Online Bank`
    }
}
</script>

<style>

</style>