<template>
  <div>
    <header class="header__nav">
      <div class="header__nav__item">
        <div class="header__nav__item__logo">Алехандро.ru</div>
      </div>
      <div class="header__nav__item">
        <a href="tel:89999989" class="header__nav__item__phone">+7 (800) 960-90-90</a>
      </div>
      <div class="header__nav__item">
        <div class="header__nav__item__menu">Menu</div>
      </div>
    </header>
  </div>
</template>

<script>
  export default {
    name: "Navbar"
  }
</script>

<style>
  .header__nav {
    display: flex;
    justify-content: space-between;
    font-size: 24px;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    height: auto;
    padding: 15px 70px;
  }

  .header__nav__item__phone {
    color: #000;
  }

</style>
