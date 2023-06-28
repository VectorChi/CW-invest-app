<template>
  <div class="navbar">
    <p class="logo">Kolò</p>
    <div class="right-nav">
      <ul>
        <li><a href="#">Invest</a></li>
        <li><a href="#">About us</a></li>
        <li><a href="#">Career</a></li>
        <li><a href="#">Contact us</a></li>
      </ul>
      <div class="nav-ctas">
        <button class="sec-btn-sml">Login</button>
        <button class="pry-btn-sml">Create account</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.logo {
  color: var(--color-black);
  font-size: 1.5rem;
  font-weight: 700;
  letter-spacing: -0.0825rem;
}
.navbar,
.right-nav,
.nav-ctas,
ul {
  display: flex;
  align-items: center;
}

.navbar {
  justify-content: space-between;
  width: 80%;
  margin: 2rem auto;
}
.right-nav {
  gap: 3rem;
}
.nav-ctas {
  gap: 0.5rem;
}
ul {
  gap: 3rem;
}
a {
  color: var(--color-grey);
  font-size: 1rem;
  letter-spacing: -0.03rem;
}
a:hover {
  color: var(--color-black);
  font-weight: 400;
}
</style>
