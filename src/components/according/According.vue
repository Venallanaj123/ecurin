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

      <!-- <div class="row">
        <div
          class="col span_1_of_2"
          v-for="(accordion, index) in accordions"
          :key="index"
        >
          <div class="accordion-element">
            <div class="accordion-element__image">
              <img :src="accordion.img" alt="card-image" />
            </div>
            <div class="accordion-element__title">
              <h2>{{ accordion.title }}</h2>
            </div>
            <div class="accordion-element__short--desription">
              <h2>{{ accordion.shortdesription }}</h2>
            </div>
          </div>
        </div>
      </div> -->
      <div class="accordion-element">
        <div class="row">
          <div class="col span_1_of_4">
            <div class="accordion-element__image">
              <img src="../../assets/images/measures/palmoil-teaser.png" />
            </div>
          </div>

          <div class="col span_3_of_4">
            <div class="accordion-element__right">
              <div class="accordion accordion-element__right--title">
                <h3>Lorem Ipsum is simply dummy text of the printing</h3>

                <p>
                  Lorem Ipsum is simply dummy text of the printing and
                  typesetting industry. Lorem Ipsum has been the industry's
                  standard dummy text ever since the 1500s, when an unknown
                  printer took a galley of type and scrambled it to make a type
                  specimen book.
                </p>
              </div>

              <div class="panel accordion-element__right--description">
                <h4 class="accordion-element__right--subtitle">
                  Dipaly accordin1 Lorem Ipsum is simply dummy text of the
                  printing
                </h4>
                <p>
                  Lorem Ipsum is simply dummy text of the printing and
                  typesetting industry. Lorem Ipsum has been the industry's
                  standard dummy text ever since the 1500s, when an unknown
                  printer took a galley of type and scrambled it to make a type
                  specimen book. Lorem Ipsum is simply dummy text of the
                  printing and typesetting industry. Lorem Ipsum has been the
                  industry's standard dummy text ever since the 1500s, when an
                  unknown printer took a galley of type and scrambled it to make
                  a type specimen book.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="accordion-element">
        <div class="row">
          <div class="col span_1_of_4">
            <div class="accordion-element__image">
              <img src="../../assets/images/measures/palmoil-teaser.png" />
            </div>
          </div>

          <!-- <div class="col span_3_of_4">
            <div class="accordion-element__right">
              <div class="accordion accordion-element__right--title">
                <h3>Lorem Ipsum is simply dummy text of the printing</h3>

                <p class="accordion-element__right--description">
                  Lorem Ipsum is simply dummy text of the printing and
                  typesetting industry. Lorem Ipsum has been the industry's
                  standard dummy text ever since the 1500s, when an unknown
                  printer took a galley of type and scrambled it to make a type
                  specimen book.
                </p>
              </div>

              <div class="panel">
                <h4 class="accordion-element__right--subtitle">
                  Lorem Ipsum is simply dummy text of the printing
                </h4>
                <p>
                  Dipaly accordin2 Lorem Ipsum is simply dummy text of the printing and
                  typesetting industry. Lorem Ipsum has been the industry's
                  standard dummy text ever since the 1500s, when an unknown
                  printer took a galley of type and scrambled it to make a type
                  specimen book. Lorem Ipsum is simply dummy text of the
                  printing and typesetting industry. Lorem Ipsum has been the
                  industry's standard dummy text ever since the 1500s, when an
                  unknown printer took a galley of type and scrambled it to make
                  a type specimen book.
                </p>
              </div>
            </div>
          </div> -->
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
          img: require("../../assets/images/measures/palmoil-teaser.png"),
          title: "Lorem Ipsum is simply dummy text of the printing ",
          shortdesription:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book",
        },
      ],
    };
  },

  props: {
    title: String,
    subtitle: String,
    content: String,
  },

  mounted() {
    const acc = document.getElementsByClassName("accordion");
    console.log(acc, "test");
    var i;

    for (i = 0; i < acc.length; i++) {
      acc[i].addEventListener("click", function () {
        this.classList.toggle("active");
        var panel = this.nextElementSibling;
        if (panel.style.display === "block") {
          panel.style.display = "none";
        } else {
          panel.style.display = "block";
        }
      });
    }
  },
};
</script>

<style lang="scss">
.accordion {
}

/*.active,
.accordion:hover {
  background-color: #ccc;
}*/

.active .accordion {
  width: 100%;
}

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

.accordion-element {
  background-color: #fafafa;
  position: relative;
  margin: 40px 0;
  &__image {
  }
  & img {
    width: 100%;
    max-width: 400px;
    height: auto;
  }
  &__right {
    color: #444;
    cursor: pointer;
    padding: 18px;
    width: 100%;
    border: none;
    text-align: left;
    outline: none;
    font-size: 15px;
    transition: 0.4s;

    &--title {
      & h3 {
        font-size: 3rem;
        margin-bottom: 10px;
        font-weight: normal;
        line-height: 4rem;
        letter-spacing: 1px;
      }
    }
    &--description {
      position: relative;
      &:after {
        content: "test";
      }
    }

    &--subtitle {
      font-size: 2rem;
      margin-bottom: 10px;

      line-height: 3rem;
    }
    &--description {
      padding: 0 18px;
      display: none;
      overflow: hidden;
    }
  }
}
</style>
