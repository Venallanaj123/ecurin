<template>
  <div>
    <nested-menu :menu="menu"></nested-menu>
  </div>
</template>

<script>
export default {
  name: "AppNested",
  components: {},
  data() {
    return {
      menu: [
        {
          label: "Home",
          path: "/",
        },
        {
          label: "Products",
          children: [
            {
              label: "Product 1",
              path: "/products/1",
            },
            {
              label: "Product 2",
              path: "/products/2",
            },
          ],
        },
        {
          label: "Contact Us",
          path: "/contact",
        },
      ],
    };
  },
};
</script>
<style scoped lang="scss">
.Menu__header {
  display: flex;
  align-items: center;
  padding-left: 35px;
  height: 50px;
  color: #fff;
  font-size: 16px;
  background-color: #232f3e;
  cursor: pointer;

  .arrow {
    padding-top: 2px;
    fill: #fff;
    margin-right: 10px;
    width: 10px;
    height: 100%;
    display: flex;
    align-items: center;
  }
}

.Menu__list {
  list-style: none;
  padding-bottom: 2px;

  .separator {
    border-bottom: 1px solid #d5dbdb;
    padding: 2px 0 0 0;
    margin: 0;
  }
}

.Menu__item {
  color: #4a4a4a;
  padding-left: 35px;
  height: 45px;
  display: flex;
  align-items: center;
  cursor: pointer;

  a {
    color: #4a4a4a;
    text-decoration: none;
  }

  .arrow {
    padding-top: 2px;
    padding-left: 15px;
    display: flex;
    align-items: center;
    width: 10px;
    height: 100%;
  }
}
</style>
