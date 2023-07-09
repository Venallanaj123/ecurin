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
          <button class="shop-cart__close-btn" @click="closeCart()">
            <i class="fa-solid fa-xmark fa-xl"></i>
          </button>
          <div class="shop-cart__amount">
            <h3 class="shop-cart__amount-title">Your shopping cart</h3>
            <span class="shop-cart__amount-count">
              (<span>{{ products.length }}</span> items)</span
            >
          </div>
        </div>

        <div v-if="hasProducts" class="shop-cart__wraper">
          <div>
            <div class="shop-cart__note">
              <p class="shop-cart__text">
                Good choice! <b>Hyaluron-Filler Skin Refining Anti-Age</b>
                <b>Serum</b> has been added to your shopping cart
              </p>
            </div>
            <ul class="shop-cart__items">
              <li
                class="shop-cart__item"
                v-for="(product, index) in products"
                :key="index"
              >
                <img
                  :src="product.img"
                  class="shop-cart__item-image"
                  style="width: 76px; height: 76px"
                />
                <div class="shop-cart__item-details">
                  <span
                    class="shop-cart__item-remove"
                    v-on:click="removeitemToCart(product)"
                  >
                    <i class="fa-solid fa-xmark fa-xl"></i>
                  </span>
                  <p class="shop-cart__item-title">{{ product.subtitle }}</p>

                  <div class="shop-cart__item-info">
                    <div class="shop-cart__item-volum">
                      <p class="shop-cart__volume-text">{{ product.volume }}</p>
                    </div>
                    <div class="shop-cart__item-quntity">
                      <span>1 pc</span>
                      <select
                        v-model="product.selectedOption"
                        class="shop-cart__item-select"
                      >
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
                  <div class="shop-cart__item-price">
                    <p class="shop-cart__item-label">Price per piece</p>
                    <div class="shop-cart__item-price-regular">
                      {{ product.price }}
                    </div>
                  </div>
                </div>
              </li>
            </ul>
          </div>
          <div>
            <ul class="shop-cart__total-price">
              <li class="shop-cart__subtotal">
                <span class="shop-cart__label-name"> Subtotal</span>
                <span class="shop-cart__calculate-price">
                  {{ calculateSubtotal }}</span
                >
              </li>
              <li class="shop-cart__shipping">
                <span class="shop-cart__shipping-name">
                  Shipping (3-5 days)</span
                >
                <span class="shop-cart__shipping-free"> FREE</span>
              </li>
              <li class="shop-cart__promotion">
                <span class="shop-cart__promotion-name">
                  Promotion: NL_EUC_Free_Shipping_EveryOrder
                </span>
              </li>
              <li class="shop-cart__promotional">
                <span class="shop-cart__promotional-code">
                  Enter a promotional code</span
                >
              </li>
            </ul>

            <div class="shop-cart__checkout-amount">
              <ul class="shop-cart__items-amounts">
                <li class="shop-cart__item-amount">
                  <p>
                    <span class="shop-cart__item-pay"> Amount payable</span>
                    <span class="shop-cart__item-incl">incl. VAT </span>
                  </p>

                  <span class="shop-cart__item-calculateSubtotal">
                    {{ calculateSubtotal }}</span
                  >
                </li>
              </ul>
            </div>
            <div class="shop-cart__checkout-button">
              <a href="" class="shop-cart__checkout-buy">
                Secure checkout

                <svg
                  class="shop-cart__checkout-svg"
                  version="1.1"
                  xmlns="http://www.w3.org/2000/svg"
                  width="32"
                  height="32"
                  viewBox="0 0 32 32"
                >
                  <path
                    d="M31.232 8.768l-15.232 12.608-15.232-12.608-0.768 0.928 15.776 13.536h0.448l15.776-13.536-0.768-0.928z"
                  ></path>
                </svg>
              </a>
            </div>
            <div class="shop-cart__options-payment">
              <div
                class="shop-cart__payemnts"
                v-for="(image, index) in images"
                :key="index"    

              >
              <img :src="image.imgsrc" alt="product-image"  class="shop-cart__payemnts-logo"/>
              </div>
             
            </div>
          </div>
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
    closeCart() { 
        this.$emit("update:cartOpen", false);
      }
   
  },

  computed: {
    hasProducts() {
      return this.products.length > 0;
    },

    calculateSubtotal() {
      let subtotal = 0;
      let price = 0;
      let quantity = 1;

      for (let i = 0; i < this.products.length; i++) {
        price = this.products[i].price.substring(1);

        if (this.products[i].selectedOption) {
          quantity = this.products[i].selectedOption;
        } else {
          this.products[i].selectedOption = "1"; //set byDefault 1
        }

        subtotal += quantity * price;
      }
      return `€${subtotal.toFixed(2)}`;
    },
  
  },

  data() {
    return {
      options: [
        { label: " 1", value: "1" },
        { label: " 2", value: "2" },
        { label: " 3", value: "3" },
        { label: " 4", value: "4" },
      ],
      selectedOption: "1", 


      images: [
        {
          imgsrc: require("../assets//images/shop/ideallogo10243x.jpg"),
        },
        {
          imgsrc: require("../assets//images/shop/mastercard.png"),
        },
        {
          imgsrc: require("../assets//images/shop/paypal.png"),
        },
        {
          imgsrc: require("../assets//images/shop/visa.png"),
        },
        {
          imgsrc: require("../assets//images/shop/logo-eshop.jpg"),
        },
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
  &__wraper {
    display: flex;
    flex-direction: column;
    height: 100%;
    justify-content: space-between;
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

  &__empty-title {
    font-size: 3.6rem;
    line-height: 4rem;
    color: #223341;
    margin-top: 25px;
    font-family: "EucerinaWgl-Demibold";
    font-weight: 600;
    text-align: center;
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
  &__items {
    position: relative;
    max-height: 480px;
    height: 100%;
    overflow: auto;
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
  &__item-details {
    padding-left: 15px;
    padding-right: 15px;
    display: inline-block;
    position: relative;
    vertical-align: top;
    width: 100%;
  }
  &__item-remove {
    right: 15px;
    position: absolute;
    left: auto;
    top: 1px;
    font-size: 1.3rem;
    cursor: pointer;
  }
  &__item-title {
    font-size: 1.8rem;
    line-height: 2rem;
    color: #223341;
    max-height: 46px;
    min-height: 46px;
    margin-bottom: 5px;
    padding-right: 20px;
    overflow: hidden;
  }
  &__item-info {
  }

  &__item-volum {
    margin-bottom: 5px;
  }
  &__volume-text {
    font-size: 1.2rem;
    line-height: 2rem;
    font-style: italic;
  }

  &__item-quntity {
    font-size: 1.2rem;
    line-height: 2rem;
  }
  &__item-select {
    padding: 10px;
    border-bottom: 1px solid #ddd;
    background-color: #fff;
    margin: 0 10px;
    background: white;
    border: 1px solid #ddd;
    padding: 2px 5px;
  }

  &__item-price {
    position: absolute;
    bottom: 1px;
    right: 15px;
    text-align: right;
  }
  &__item-label {
    font-size: 1.2rem;
    line-height: 1.6rem;
    margin-bottom: 3px;
  }

  &__item-price-regular {
    color: #213242;
    font-size: 1.8rem;
    line-height: 2.7rem;
    font-weight: bold;
    font-family: " EucerinaWgl-Demibold";
  }


  &__subtotal {
    @include list-products;
  }
  &__subtotal::before {
    @include before;
  }

  &__shipping {
    @include list-products;
  }

  &__shipping::before {
    @include before;
  }
  &__promotion {
    @include list-products;
  }
  &__promotion::before {
    @include before;
  }

  &__promotional {
    @include list-products;
  }
  &__promotional::before {
    @include before;
  }

  &__item-amount {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 20px;
    font-family: "EucerinaWgl-Demibold";
    font-size: 2.5rem;
    line-height: 3rem;
    color: #223341;
  }
  &__item-amount::before {
    @include before;
  }

  &__item-pay {
    font-family: "EucerinaWgl-Demibold";
    font-size: 2.5rem;
    line-height: 3rem;
    color: #223341;
  }
  &__item-incl {
    margin-left: 5px;
  }
  &__checkout-button {
    margin: 20px 0;
  }
  &__checkout-buy {
    background-color: #96042d;
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    width: 100%;
    font-weight: bold;
  }
  &__checkout-svg {
    fill: #fff !important;
    transform: rotate(-45deg);
    -webkit-transform: rotate(-90deg);
    height: 10px;
    width: 20px;
    stroke-width: 3px;
    stroke: #fff;
    vertical-align: middle;
  }
  &__options-payment {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &__payemnts{
    margin: 10px;
  }
}
</style>
