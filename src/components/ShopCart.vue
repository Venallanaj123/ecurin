<template>
  <div class="shop-cart">
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
            <span class="shop-cart__amount-count">
              (<span>{{ products.length }}</span> items)</span
            >
          </div>
        </div>
    
        <div v-if="hasProducts">
          <div class="shop-cart__note">
            <p class="shop-cart__text">
              Good choice! <b>Hyaluron-Filler Skin Refining Anti-Age</b>
              <b>Serum</b> has been added to your shopping cart
            </p>
          </div>
          <ul class="shop-cart__full" v-if="hasProducts">
            <li  class="shop-cart__item"  v-for="(product, index) in products" :key="index">
              <img
                :src="product.img"
                class="shop__cart-image"
                style="width: 76px; height: 76px"
              />
              <div class="shop-cart__details">
                <span
                  class="shop-cart__remove"
                  v-on:click="removeitemToCart(product)"
                >
                  <i class="fa-solid fa-xmark fa-xl"></i>
                </span>
                <p class="shop-cart__name">{{ product.subtitle }}</p>

                <div class="shop-cart__info">
                  <div class="shop-cart__volume">
                    <p class="shop-cart__volume-text">{{ product.volume }}</p>
                  </div>
                  <div class="shop-cart__quntity">
                    <span>1 pc</span>
                    <select v-model="selectedOption" class="shop-cart__seclect">
                      <option value="">1</option>
                      <option
                        v-for="(option, index) in options"
                        :key="index"
                        :value="option.value"
                      >
                        {{ option.label }}
                      </option>
                    </select>
                  </div>
                </div>
                <div class="shop-cart__price">
                  <p class="shop-cart__price-label">Price per piece</p>
                  <div class="shop-cart__price-regular">
                    {{ product.price }}
                  </div>
                </div>
              </div>
            </li>
          </ul>

       <ul class="shop-cart__total-price">
         <li class="shop-cart__subtotal">
          <span class="shop-cart__label-name"> Subtotal</span>
          <span  class="shop-cart__calculate-price"> €42.49</span>
         </li>
         <!-- <li class="shop-cart__subtotal">
          <span class="shop-cart__label-name"> Subtotal</span>
          <span  class="shop-cart__calculate-price"> €53.98</span>
         </li>
         <li class="shop-cart__subtotal">
          <span class="shop-cart__label-name"> Subtotal</span>
          <span  class="shop-cart__calculate-price"> €53.98</span>
         </li>
         <li class="shop-cart__subtotal">
          <span class="shop-cart__label-name"> Subtotal</span>
          <span  class="shop-cart__calculate-price"> €53.98</span>
         </li> -->
       </ul>
        
        </div>
 
        <div
          class="shop-cart__empty"
          v-bind:style="{ display: !hasProducts ? 'block' : 'none' }"
        >
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
  </div>
</template>
<script>
export default {
  name: "ShopCart",
  props: ["products", "isCartOpen"],

  methods: {
    removeitemToCart(product) {
      console.log(product);
      this.$emit("removeitemToCart", product);
    },
  },
  computed: {
    hasProducts() {
      return this.products.length > 0;
    },
   
  },

  data() {
    return {
      // isCartOpen: false,
      selectedOption: "",
      options: [
        { label: " 2", value: "2" },
        { label: " 3", value: "3" },
        { label: " 4", value: "4" },
      ],
    };
  },
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
  &__full {
    position: relative;
  }

  &__item {
    box-shadow: 0 0 4px 2px #f3f4f5;
    border: 2px solid #f3f4f5;
    border-radius: 7px;
    display: -webkit-box;
    display: flex;
    margin-bottom: 10px;
    padding: 17px 0 17px 5px;
  }
  &__details {
    padding-left: 15px;
    padding-right: 15px;
    display: inline-block;
    position: relative;
    vertical-align: top;
    width: 100%;
  }
  &__remove {
    right: 15px;
    position: absolute;
    left: auto;
    top: 1px;
    font-size: 1.3rem;
  }
  &__name {
    font-size: 1.8rem;
    line-height: 2rem;
    color: #223341;
    max-height: 46px;
    min-height: 46px;
    margin-bottom: 5px;
    padding-right: 20px;
    overflow: hidden;
  }
  &__info {
  }
  &__volume {
    margin-bottom: 5px;
  }
  &__volume-text {
    font-size: 1.2rem;
    line-height: 2rem;
    font-style: italic;
  }

  &__price {
    position: absolute;
    bottom: 1px;
    right: 15px;
    text-align: right;
  }
  &__quntity {
    font-size: 1.2rem;
    line-height: 2rem;
  }
  &__seclect {
    padding: 10px;
    border-bottom: 1px solid #ddd;
    background-color: #fff;
    margin: 0 10px;
    background: white;
    border: 1px solid #ddd;

    padding: 2px 5px;
  }

  &__price {
  }
  &__price-label {
    font-size: 1.2rem;
    line-height: 1.6rem;
    margin-bottom: 5px;
  }

  &__price-regular {
    color: #213242;
    font-size: 1.8rem;
    line-height: 2.7rem;
    font-weight: bold;
    font-family: " EucerinaWgl-Demibold";
  }
  &__note {
    position: relative;
    margin-top: 10px;
    margin-bottom: 10px;
  }
  &__note::before {
    content: "";
    margin-left: -20px;
    margin-right: -20px;
    padding-left: 20px;
    padding-right: 20px;
    background-color: #50c245;
    position: absolute;
    width: 100%;
    height: 100%;
    z-index: -1;
  }
  &__note::after {
    content: "";
    border: solid #fff;
    border-width: 0 3px 3px 0;
    height: 15px;
    position: absolute;
    width: 7px;
    transform: rotate(45deg);
    top: 50%;
    transform: rotate(45deg) translate(-50%, -50%);
    z-index: 9;
  }
  &__text {
    color: white;
    font-size: 1.2rem;
    line-height: 1.5rem;
    padding: 10px 0 10px 40px;
  }

  span {
    cursor: pointer;
  }

  &__subtotal{
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative;
    color: #4e5c67;
    padding-top: 10px;
    padding-bottom: 10px;
    font-size: 1.6rem;
    line-height: 2rem;
  }

  &__subtotal::before{
    content: "";
    background-color: #d2d5d8;
    height: 1px;
    top: 0;
    position: absolute;
    width: 100%;
  }
}
</style>
