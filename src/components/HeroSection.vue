<template>
  <div class="main-hero">
    <div class="right-hero">
      <div class="big-copy-container">
        <h1 class="big-copy-black">Invest in mutual funds.</h1>
        <div class="purple-accent">
          <h1 class="big-copy-white">Grow wealth.</h1>
        </div>
        <div class="sub-copy-container">
          <p class="sub-copy-hero">
            Take charge of your finances and grow your income. Start investing
            with as low as ₦500.
          </p>
          <button class="pry-btn-big">Invest now</button>
        </div>
      </div>
    </div>
    <img src="../assets/images/Hero-image.png" alt="hero-image" />
  </div>
</template>

<style scoped>
.main-hero {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 7.5rem auto;
  width: 80%;
}
.right-hero,
.big-copy-container,
.sub-copy-container {
  display: flex;
  flex-direction: column;
}
.right-hero {
  width: 35%;
  gap: 3rem;
}
.big-copy-container {
  gap: 1rem;
}
.sub-copy-container {
  gap: 2.2rem;
}
h1 {
  font-size: 4.5rem;
  font-weight: 700;
  line-height: 105.523%;
  letter-spacing: -0.2475rem;
}

.big-copy-black {
  color: var(--color-black);
}
.big-copy-white {
  color: var(--color-white);
}
.purple-accent {
  display: flex;
  padding: 0.2rem 1.2rem;
  background-color: var(--color-purple);
}
.pry-btn-big {
  width: 30%;
}
.sub-copy-hero {
  font-size: 1.2rem;
  color: var(--color-grey);
  line-height: 162.023%;
  letter-spacing: -0.0375rem;
}
img {
  image-rendering: optimizeQuality;
  filter: grayscale(1);
}
</style>
