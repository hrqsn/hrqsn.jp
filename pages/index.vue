<template>
  <div>
    <!-- <header class="header">
      <div class="emoji">
        <span>🎁</span>
        <span>🤠</span>
        <span>🤖</span>
        <span>👻</span>
        <span>🦊</span>
        <span>🧠</span>
        <span>🤡</span>
        <span>👁</span>
        <span>👨‍💻</span>
        <span>😎</span>
      </div>
    </header> -->
    <div class="container">
      <section class="cards">
        <div class="grid">
          <div class="item" v-for="item in items" :key="item.id">
            <hr-card :type="item.type" :media="media(item)" :title="item.title" :text="item.text" :color="item.color" :href="item.link"/>
          </div>
        </div>
      </section>
    </div>
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
.header {
  height: 240px;
  display: flex;
  justify-content: center;
  .emoji {
    margin-top: 88px;
    display: flex;
    flex-direction: column;
    font-size: 64px;
    animation-duration: 0s;
    animation: transform 10s linear infinite;
  }
}
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
