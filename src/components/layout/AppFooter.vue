<template>
  <footer>
    <div class="container">
      <div class="footer">
        <div class="row">
          <div class="span_2_of_2">
            <div class="footer__logo">
              <img
                src="../../assets/images/logo.svg"
                class="footer_logo--ecurin"
                alt="brand logo ecurin"
              />
            </div>
          </div>
        </div>
        <div class="row">
          <div class="span_2_of_2">
            <div class="footer__social">
              <a href="#" class="footer__social-item">
                <img
                  src="../../assets/images/facebook.svg"
                  alt=""
                  width="25px"
                  height="25px"
                />
              </a>
              <a href="#" class="footer__social-item">
                <img
                  src="../../assets/images/instagram.svg"
                  alt=""
                  width="25px"
                  height="25px"
                />
              </a>
              <a href="#" class="footer__social-item">
                <img
                  src="../../assets/images/youtube.svg"
                  alt=""
                  width="25px"
                  height="25px"
                />
              </a>

              <a href="#" class="footer__social-item">
                <img
                  src="../../assets/images/pinterest.svg"
                  alt=""
                  width="25px"
                  height="25px"
                />
              </a>
              <a href="#" class="footer__social-item">
                <img
                  src="../../assets/images/tiktok.svg"
                  alt=""
                  width="25px"
                  height="25px"
                />
              </a>
            </div>
          </div>
        </div>

        <div class="row">
          <div class="span_2_of_2">
            <nav class="footer__nav">
              <ul class="footer__menu">
                <li class="footer__menu-item"><a href="#">Contact</a></li>
                <li class="footer__menu-item"><a href="#">imprint</a></li>
                <li class="footer__menu-item">
                  <a href="#">Data protection</a>
                </li>
                <li class="footer__menu-item"><a href="#">Terms of Use</a></li>
                <li class="footer__menu-item">
                  <a href="#">Cookies settings</a>
                </li>
              </ul>
            </nav>
          </div>
        </div>
        <hr class="hr" />

        <div class="row">
          <div class="footer__bottom span_1_of_2">
            <div class="footer__logo--left">
              <img src="../../assets/images/Beiersdorf-Logo.png" alt="" />
            </div>
          </div>
          <div class="footer__bottom--right span_1_of_2">
            <nav class="footer__nav right">
              <ul class="footer__list">
                <li class="footer__item"><a href="#">About Us</a></li>
                <li class="footer__item"><a href="#">About Us</a></li>
                <li class="footer__item-copyright">
                  <span class="copy-right">COPYRIGHT © BEIERSDORF 2023</span>
                </li>
              </ul>
            </nav>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "AppFooter",
};
</script>

<style scoped lang="scss">
@import "../../assets/scss/grid/grid";

footer {
  padding: 50px 0;
  position: relative;

  .footer {
    &__logo {
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 10px;

      & img {
        width: 100%;
        max-width: 100px;
        height: auto;
      }
    }

    &__social {
      display: flex;
      justify-content: center;
      align-items: center;
      margin-bottom: 10px;

      &-item {
        padding: 0 10px;
      }
    }
    &__nav {
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
    }
    & ul {
      list-style: none;

      & li {
        padding: 0 10px;
        display: inline;
      }
    }

    & a {
      text-transform: uppercase;
      font-size: 1.2rem;
      color: $grey-light;
      text-decoration: underline #a7adb3;
    }

    & a:hover {
      text-decoration: none;
    }
    &__bottom {
      padding-top: 10px;
      padding-bottom: 10px;
    }
  }
}

.footer__item-copyright {
  font-size: 1.2rem;
  line-height: 1.7rem;
  color: #767676;
  text-transform: uppercase;
}
.right {
  float: right;
}

@media only screen and (max-width: 768px) {
  .footer {
    &__logo {
      &--left {
        display: flex;
        justify-content: center;
      }
    }
  }
}
</style>
