<template>
  <component :is="tag" :href="href" :color="color" class="card" target="_blank" rel="noopener">
    <div class="container">
      <img :src="media" alt="" class="img">
      <iframe v-if="type==='music'" :src="media" width="100%" height="256" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>
      <iframe v-if="type==='video'" width="100%" height="256" :src="media" frameborder="0" allow="encrypted-media;"></iframe>
      <h1 class="title">{{title}}</h1>
      <p class="text">{{text}}</p>
    </div>
  </component>
</template>

<script>
export default {
  name: 'HrCard',
  props: {
    href: {
      type: String,
      default: undefined
    },
    color: {
      type: String,
      default: 'default'
    },
    media: {
      type: String,
      default: require('@/assets/img/0.png')
    },
    title: String,
    text: String,
    type: String
  },
  computed: {
    tag() {
      return this.href ? 'a' : 'div'
    }
  }
}
</script>

<style scoped lang="scss">
.card {
  text-decoration: none;
  border: 2px solid $primary;
  box-shadow: 5px 6px 0px $primary;
  display: block;
  .container {
    padding: 16px;
    .img {
      width: 100%;
      height: 240px;
      object-fit: cover;
    }
    .title {
      font-size: rem(24px);
      margin-top: 8px;
    }
    .text {
      font-size: 16px;
      margin-top: 8px;
      font-style: italic;
    }
  }
  &:hover {
    margin-left: 5px;
    margin-top: 6px;
    box-shadow: 0px 0px 0px transparent !important;
    margin-right: -5px;
    margin-bottom: -6px;
  }
  &[color='black'] {
    border: 2px solid $black;
    box-shadow: 5px 6px 0px $black;
  }
  &[color='blue'] {
    border: 2px solid $primary;
    box-shadow: 5px 6px 0px $primary;
  }
}
</style>
