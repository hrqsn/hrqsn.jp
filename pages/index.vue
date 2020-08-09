<template>
  <div class="container">
    <section class="cards">
      <div class="grid">
        <div class="item" v-for="item in items" :key="item.id">
          <hr-card :type="item.type" :media="media(item)" :title="item.title" :text="item.text" :color="item.color" :href="item.link"/>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import HrCard from '@/components/Card'
import items from '@/assets/items.json'
export default {
  components: {
    HrCard
  },
  data() {
    return {
      items: items
    }
  },
  methods: {
    media(item) {
      if (item.type!=="default") {
        return item.media
      } else {
        return require(`@/assets/img/${item.media}`)
      }
    }
  }
}
</script>

<style scoped lang="scss">
.cards {
  padding: 120px 24px;
  .grid {
    display: grid;
    grid-gap: 32px;
    grid-template-columns: repeat(2, auto);
    justify-content: center;
    .item {
      max-width: 368px;
      width: 100%;
      z-index: 100;
      background-color: #fff;
    }
  }
  @include mqdown {
    .grid {
      grid-template-columns: repeat(1 ,auto);
    }
  }
}
</style>
