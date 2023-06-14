<template>
  <section class="shop-cart">
    <div class="shop-cart__toggle">
      <button @click="isCartOpen = !isCartOpen" class="shop-cart__toggle-btn">
        <svg
          class="shop-cart__toggle-svg"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          width="26"
          height="30"
          viewBox="0 0 32 32"
        >
          <path
            d="M16 2.182c3.213 0 5.818 2.605 5.818 5.818v1.455h2.909l2.182 19.636h-21.818l2.182-19.636h2.909v-1.455c0-3.213 2.605-5.818 5.818-5.818zM23.425 10.909h-14.852l-1.858 16.727h18.568l-1.858-16.727zM16 3.636c-2.355 0-4.275 1.866-4.361 4.2l-0.003 0.164v1.455h8.727v-1.455c0-2.41-1.953-4.364-4.364-4.364z"
          ></path>
        </svg>
      </button>

      <div
        class="shop-cart__content"
        :class="{ 'shop-cart__content--open': isCartOpen }"
      >
        <div class="shop-cart__header">
          <button class="shop-cart__close-btn" @click="isCartOpen = false">
            <i class="fa-solid fa-xmark fa-xl"></i>
          </button>
          <div class="shop-cart__amount">
            <h3 class="shop-cart__amount-title">Your shopping cart</h3>
            <span class="shop-cart__amount-count"> (<span>0</span> items)</span>
          </div>
        </div>
        <div class="shop-cart__empty">
          <h2 class="shop-cart__empty-title">
            Your shopping<br />
            cart is empty
          </h2>

          <div class="shop-cart__empty-bag">
            <img src="../assets/images/shop/empty-shopping-cart.png" alt="" />
          </div>
          <div class="shop-cart__empty-text">
            <p>Shop in our product section to add items to your basket.</p>
          </div>
          <a href="#" class="shop-cart__button">View products</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AddCart",
  data() {
    return {
      isCartOpen: false,
    };
  },

  /* methods: {
    addCard() {

      let addCard;
      let addcard = document.querySelector(".addcard");
      let cardlist = document.querySelector(".cardlist");

      addcard.addEventListener("click", addCard);
      addcard.classList.toggle("active");
      cardlist.classList.toggle("active");
    },
  },*/
};
</script>

<style lang="scss" scoped>
.shop-cart {
  display: flex;
  align-items: center;
  justify-content: center;
  &__toggle {
  }
  &__toggle-btn {
    cursor: pointer;
    border: none;
    background: white;
  }

  svg {
    fill: #7a858d;
  }
  &__content {
    position: fixed;
    top: 0;
    right: 0;
    background-color: #fff;
    height: 100vh;
    max-height: 100%;
    padding: 20px;
    z-index: 9999;
    display: -webkit-box;
    display: flex;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    flex-direction: column;
    -webkit-box-pack: justify;
    width: 375px;
    box-shadow: -4px -1px 6px -2px rgba(0, 0, 0, 0.1);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease-in-out;
    right: -100%;
  }
  &__content--open {
    opacity: 1;
    visibility: visible;
    transition: all 0.4s ease-in-out;
    right: 0;
  }

  &__header {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  &__amount {
    display: flex;
    align-items: center;
  }
  &__amount-title {
    color: #223341;
    -webkit-box-flex: 1;
    flex: auto;
    font-size: 2.4rem;
    line-height: 3.2rem;
    font-family: "EucerinaWgl-Demibold";
    font-weight: 600;
    padding: 0 30px;
  }

  &__amount-count {
    font-size: 1.6rem;
    line-height: 1.9rem;
    color: #4e5c67;
  }
  &__close-btn {
    border: none;
    background: white;
    cursor: pointer;
  }
  &__empty {
  }
  &__empty-title {
    font-size: 3.6rem;
    line-height: 4rem;
    color: #223341;
    margin-top: 25px;
    font-family: "EucerinaWgl-Demibold";
    font-weight: 600;
    text-align: center;
  }
  &__empty-bag {
    margin-left: auto;
    margin-right: auto;
    max-width: 295px;
  }
  img {
    margin-left: auto;
    margin-right: auto;
    max-width: 295px;
  }
  &__empty-text {
    margin-top: 10px;
    text-align: center;
    color: #223341;
  }
  &__button {
    background-color: #96042d;
    color: white;
    border: none;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 1.6rem;
    line-height: 1.9rem;
    width: 100%;
    margin-top: 25px;
    font-weight: 600;
  }
}
</style>
