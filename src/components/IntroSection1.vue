<template>
  <section class="intro-section1">
    <div class="container">
      <div class="intro">
        <p class="intro-section1">Lorem ipsum dolor sit.</p>
        <h1 class="p-head">Lorem ipsum dolor sit amet.</h1>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Amet, at.
        </p>
        <a href="#" class="btn">Rezervo a table</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "IntroSection1",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.intro-section1 {
  background-image: url("../assets/images/intro-section-background.jpg");
  //   height: 500px;
  height: 60vh;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;

  //   &__element {
  //     width: 100%;
  //     padding: 10rem 0;

  //     &--heading {
  //       font-size: 3rem;
  //       font-weight: bold;
  //       margin-bottom: 10px;
  //     }

  //     &--text {
  //       font-size: 1.6rem;
  //       margin-bottom: 15px;
  //     }

  //     & button {
  //       @include button;
  //       padding: 7px 50px;
  //     }

  //     & button:hover {
  //       background-color: $danger-dark;
  //     }
  //   }
}

.intro {
  width: 55%;
  border-radius: 5px;
  background-color: rgba(0, 0, 0, 0.5);
  padding: 5rem 2rem;
}

.intro .intro-text {
  color: #bb2205;
  font-weight: 700;
  font-size: 1.7rem;
  text-transform: uppercase;
}
.p-head {
  color: white;
  text-transform: capitalize;
  font-size: 2.8rem;
  margin-bottom: 1rem;
  font-weight: 700;
  letter-spacing: 3px;
}

.white-text {
  color: white;
  margin-bottom: 2.5rem;
}

.btn {
  font-size: 1.6rem;
  font-weight: 500;
  text-decoration: none;
  color: white;
  border-radius: 5px;
  border-color: transparent;
  border: 1px solid #fff;
  padding: 0.8rem 1.6rem;
}
.btn:hover {
  background-color: #bb2205;
}

@media only screen and (max-width: 768px) {
  .intro-section1 {
    width: 100%;
    height: 100%;
  }
}
</style>
