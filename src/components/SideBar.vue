<template>
  <div class="sidebar">
    <div class="sidebar__menu">
      <ul class="menu">
        <li class="menu__item">Elements</li>
        <li class="menu__item">Text</li>
        <li class="menu__item">Photo</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "SideBar",
  data() {
    return {
      isOpen: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.sidebar {
  width: 230px;
  background: lightblue;
  height: 100vh;
  &__menu > ul {
    text-align: left;
  }
}
.menu {
  &__item {
    line-height: 1.5rem;
  }
}
</style>
