<template>
  <section>
    <div class="container">
      <div class="row">
        <div class="col span_2_of_2">
          <div class="accordion">
            <h1 class="accordion__title">
              {{ title }}
            </h1>
            <h3 class="accordion__subtitle">
              {{ subtitle }}
            </h3>
            <div class="accordion__content">
              <p>{{ content }}</p>
            </div>
          </div>
        </div>
      </div>

      <div class="row bg-row">
        <div
          class="col span_2_of_2"
          v-for="(accordion, index) in accordions"
          :key="index"
        >
          <div class="accordion-element" @click="toggleAccordion(index)">
            <div class="accordion-element__image">
              <img :src="accordion.img" alt="card-image" />
            </div>
            <div class="accordion-element__details">
              <div class="accordion-element__title">
                <h3>{{ accordion.title }}</h3>
              </div>
              <div class="accordion-element__short--desription">
                <p>{{ accordion.shortdesription }}</p>
              </div>
            </div>

            <div
              class="accordion-element__learn-more"
              v-show="!accordion.isOpen"
            >
              <span @click.stop="toggleAccordion(index)">
                Learn more <i class="fa fa-chevron-down"></i>
              </span>
            </div>
          </div>
          <div
            v-show="accordion.isOpen"
            :class="{
              'accordion-element__long-description--open': accordion.isOpen,
            }"
            class="accordion-element__long-description"
            :style="{
              transition: accordion.isOpen
                ? 'max-height 0.5s ease-out'
                : 'max-height 0.2s ease-in',
            }"
          >
            <h4>{{ accordion.subtitle }}</h4>
            <p>{{ accordion.longdescription }}</p>
            <p>{{ accordion.longdescriptiononline }}</p>
            <br />
            <h4>{{ accordion.subtitle }}</h4>

            <p>{{ accordion.longdescription }}</p>

            <div
              class="accordion-element__learn-less"
              v-if="showLearnLess(index)"
            >
              <span @click.stop="toggleAccordion(index)">
                Learn less <i class="fa fa-chevron-up"></i>
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Accordion",
  data() {
    return {
      accordions: [
        {
          id: "1",
          img: require("../../assets/images/measures/palmoil-teaser.png"),
          title: "Lorem Ipsum is simply dummy text of the printing ",
          shortdesription:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book",
          subtitle:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry",

          longdescription:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
          longdescriptiononline:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry lorem Ipsum is simply dummy text of the printing and typesetting industry",
          isOpen: false,
        },
      ],
    };
  },
  methods: {
    toggleAccordion(index) {
      this.accordions[index].isOpen = !this.accordions[index].isOpen;
    },

    showLearnLess(index) {
      return (
        this.accordions[index].longdescription &&
        this.accordions[index].longdescription.length > 0
      );
    },
  },
  props: {
    title: String,
    subtitle: String,
    content: String,
  },
};
</script>

<style lang="scss">
.accordion {
  padding: 30px;

  &__title {
    font-size: 3.6rem;
    margin-bottom: 20px;
    font-weight: normal;
    line-height: 5rem;
    letter-spacing: 1px;
  }

  &__subtitle {
    font-size: 2.4rem;
    margin-bottom: 20px;
    font-weight: normal;
    line-height: 3.6rem;
    letter-spacing: 0.5px;
  }

  &__content {
    letter-spacing: 0.2px;
  }
}

/**** START TO STYLE ACCORDIN ****/
.accordion-element {
  position: relative;
  display: flex;
  align-items: center;
  margin-bottom: 40px;
  padding: 30px 20px;

  &__image {
    margin-right: 20px;
  }
  img {
    width: 100%;
    max-width: 400px;
    height: auto;
  }
  &__details {
    flex-grow: 1;
  }
  &__title h3 {
    color: #444;
    font-size: 2.4rem;
    line-height: 3rem;
    font-weight: 500;
    margin-bottom: 10px;
  }
  &__short--desription {
  }
  &__learn-more {
    position: absolute;
    bottom: 10px;
    right: 20px;
    cursor: pointer;
    color: $textcolor;
    font-weight: bold;
    font-size: 1.6rem;
    line-height: 2.4rem;

    .fa-chevron-down {
      margin-left: 5px;
      transition: transform 0.3s ease;
    }
  }

  &__long-description {
    padding-right: 20px;
    padding-left: 20px;
    padding-top: 30px;
    padding-bottom: 50px;
    max-height: 0;
    overflow: hidden;
    opacity: 0;
    max-height: 0;
    transition: all 0.3s ease;

    &--open {
      opacity: 1;
      margin-top: 1rem;
      max-height: 100%;
      transition: all 0.5s ease-in-out;
    }
    h4 {
      font-size: 2rem;
      line-height: 2.7rem;
      color: #444;
      margin-bottom: 5px;
    }
  }

  &__learn-less {
    display: flex;
    align-items: center;
    justify-content: end;
    cursor: pointer;
    color: $textcolor;
    font-weight: bold;
    font-size: 1.6rem;
    line-height: 2.4rem;
    .fa-chevron-up {
      transition: transform 0.3s ease;
      margin-left: 5px;
    }
  }
}
.accordion-element__learn-more span:hover .fa-chevron-down,
.accordion-element__learn-less span:hover .fa-chevron-up {
  transform: rotate(180deg);
}

.bg-row {
  background-color: #fafafa;
}
</style>
