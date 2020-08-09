<template>
  <div>
    <section class="falling">
      <ul class="emoji">
        <li>🤠</li>
        <li>🤖</li>
        <li>👻</li>
        <li>🦊</li>
        <li>🧠</li>
        <li>🤡</li>
        <li>👁</li>
        <li>👨‍💻</li>
        <li>😎</li>
        <li>🤩</li>
      </ul>
    </section>
    <Nuxt />
  </div>
</template>

<style scoped lang="scss">
.emoji {
  position: absolute;
  top: -100px;
  height: calc(100% + 100px);
  width: 100%;
  margin: 0;
  padding: 0;
  li {
    position: absolute;
    list-style: none;
    display: block;
    font-size: 32px;
    border-radius: 50%;
    animation-duration: 8s;
    animation: fall 30s linear infinite;
    left: 6%;
    &:nth-child(1) {
      left: 25%;
      font-size: 64px;
      animation-duration: 16s;
      animation: fallx 20s linear infinite;
    }
    &:nth-child(2) {
      left: 60%;
      font-size: 40px;
      animation-delay: 40s;
    }
    &:nth-child(3) {
      left: 42%;
      animation-delay: 64s;
      animation: fallx 32s linear infinite;
    }
    &:nth-child(4) {
      left: 78%;
      font-size: 72px;
      animation-delay: 80s;
      animation: fallx 60s linear infinite;
    }
    &:nth-child(5) {
      left: 76%;
      font-size: 50px;
      animation-delay: 96s;
      animation: fallx 40s linear infinite;
    }
    &:nth-child(6) {
      left: 80%;
      font-size: 32px;
      animation-delay: 120s;
    }
    &:nth-child(7) {
      left: 16%;
      animation-delay: 140s;
      font-size: 56px;
      animation: fallx 32s linear infinite;
    }
    &:nth-child(8) {
      left: 24%;
      animation-delay: 156s;
      animation: fallx 24s linear infinite;
    }
    &:nth-child(9) {
      left: 70%;
      font-size: 64px;
      animation-delay: 164s;
    }
    &:nth-child(10) {
      left: 30%;
      font-size: 32px;
      animation-delay: 180s;
      animation: fallx 16s linear infinite;
    }
  }
}
</style>
