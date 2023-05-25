<template>
  <section class="product-detail">
    <div class="container">
      <div class="row">
        <div
          class="col span_1_of_2"
          v-for="(image, index) in images"
          :key="index"
        ></div>
        <div
          class="col span_1_of_2"
          v-for="(product, index) in products"
          :key="index"
        >
          <div class="product-detail__description">
            <h1 class="product-detail__title">
              {{ product.title }}
            </h1>
            <p class="product-detail__quantity">
              {{ product.quantity }}
            </p>
            <!-- <div class="product-block">
              <p class="product-nivea__description--price price">
                {{ product.price }}
              </p>
              <i
                class="fas fa-info-circle"
                @mouseenter="showTooltip = true"
                @mouseleave="showTooltip = false"
              ></i>
              <div class="tooltip" v-if="showTooltip">
                <p>This is more information about the product.</p>
              </div>
            </div> -->
            <div class="product-detail__price">
              <div class="product-detail__price--wraper">
                <span class="price"> {{ product.price }}</span>
                <i
                  class="fas fa-info-circle"
                  @mouseenter="showTooltip = true"
                  @mouseleave="showTooltip = false"
                ></i>
                <span class="tooltip" v-if="showTooltip">
                  <h3>{{ product.heading }}</h3>
                  <p class="content">{{ product.content }}</p>
                </span>
              </div>
            </div>
            <p class="discount">{{ product.discount }}</p>
            <select v-model="selectedOption" class="custom-select">
              <option value="">1</option>
              <option
                v-for="(option, index) in options"
                :key="index"
                :value="option.value"
              >
                {{ option.label }}
              </option>
            </select>

            <p class="availability">{{ product.availability }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppNivea",
  data() {
    return {
      showTooltip: false,

      products: [
        {
          title: "schutzund pflege sonnenspray ",

          quantity: " lichtschutzfaktor 30|200 ml",

          price: "10,72 €",
          heading: "Notice",
          content: "Incl. 19.00% VAT plus 3.95 €  shipping costs",
          href: "shipping costs",
          discount: "1| 53,60 €",
          availability: "availability",
        },
      ],
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
@import "../../assets/scss/grid/grid";
$basecolor: #0032a0;

.container {
  max-width: 1200px;
  margin: 0 auto;
}
.row {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.product-detail {
  display: flex;
  justify-content: space-between;
  align-items: center;

  &__description {
    padding: 20px;
  }
  &__title {
    color: $basecolor;
    text-transform: uppercase;
    margin-top: 0;
    font-size: 3.6rem;
    line-height: 4.2rem;
    margin-bottom: 8px;
    font-weight: bold;
  }
  &__quantity {
    color: $basecolor;
    font-weight: bold;
    margin-bottom: 8px;
  }
  &__price {
    position: relative;
    display: flex;
    align-items: center;
    margin-bottom: 5px;
  }
  &-wraper {
    padding: 40px;
  }
  .price {
    color: $basecolor;
    font-weight: bold;
    margin-bottom: 8px;
    font-size: 1.8rem;
    line-height: 2.1rem;
  }
  .fas {
    margin-left: 10px;
    font-size: 15px;
  }
  .tooltip {
    position: absolute;
    top: 100%;
    width: 70%;
    height: auto;
    left: 50%;
    transform: translateX(-50%);
    padding: 10px 20px;
    background-color: #eff5fa;
    border: 1px solid #d6dcec;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.12);
    z-index: 999;
    display: none;
    margin-left: -30px;
    border-radius: 3px;
  }
  h3 {
    font-size: 1.6rem;
    color: $basecolor;
    line-height: 1.9rem;
    font-weight: bold;
    text-transform: uppercase;
    margin-bottom: 5px;
  }
  .content {
    color: $basecolor;
    font-size: 1.4rem;
  }

  .fas.fa-info-circle:hover + .tooltip {
    display: block;
  }
  .discount {
    color: $basecolor;
    font-weight: normal;
    margin-bottom: 8px;
    font-size: 1.8rem;
    line-height: 2.1rem;
  }

  .custom-select {
    background-color: #f5f5f5;
    border: none;
    color: $basecolor;
    /*padding: 12px;*/
    width: 60px;
    padding: 2px 16px 2px 8px;
    font-size: 16px;
    cursor: pointer;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
    margin-bottom: 8px;
  }
  .availability::before {
    content: "\2022";
    color: green;
    margin-right: 5px;
  }
}
</style>
