<template>
  <div class="container">
    <section class="cards">
      <div class="grid">
        <div class="item" v-for="work in works" :key="work.id">
          <hr-work-card :media="media(work)" :title="work.title" :text="work.text" :color="work.color" :href="work.link" :description="work.description" :type="work.type"/>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import HrWorkCard from '@/components/WorkCard'
import works from '@/assets/works.json'
export default {
  components: {
    HrWorkCard
  },
  data() {
    return {
      works: works
    }
  },
  methods: {
    media(item) {
      if (item.type!=="img") {
        return item.media
      } else {
        return require(`@/assets/img/works/${item.media}`)
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
