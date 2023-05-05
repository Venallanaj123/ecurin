<template>
  <header>
    <div class="container">
      <div class="header">
        <div class="header-logo">
          <img src="../../assets/images/logo.svg" alt="" class="nav-logo" />
        </div>
        <div class="header-left-mobile">
          <div class="hamburger" @click="showMenuMobile()">
            <span class="bar"></span>
            <span class="bar"></span>
            <span class="bar"></span>
          </div>
        </div>
        <div class="header-logo-center">
          <img src="../../assets/images/logo.svg" alt="" class="nav-logo" />
        </div>
        <nav class="navbar-mobile">
          <ul class="nav-menu">
            <!-- <li><a href="@">test</a></li> -->
          </ul>
        </nav>

        <nav
          class="uk-navbar-center cp-navigation desktop-nav nav-overlay desktop-visible"
        >
          <ul class="cp-first-level-nav uk-navbar-nav uk-visible@s">
            <li class="">
              <a href="/produkte" class=""
                ><font style="vertical-align: inherit"
                  ><font style="vertical-align: inherit">Products</font></font
                ></a
              >

              <div
                class="uk-navbar-dropdown cp-second-level-nav-wrapper uk-navbar-dropdown-dropbar uk-navbar-dropdown-stack uk-navbar-dropdown-bottom-left menu-aim--delaying"
              >
                <ul class="uk-nav uk-navbar-dropdown-nav cp-second-level-nav">
                  <li class="menu-aim__item menu-aim__item--active">
                    <a href="/produkte"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >product line</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    >
                      <div class="cp-third-level-nav-content">
                        <ul class="cp-third-level-nav">
                          <li>
                            <a href="/produkte/actinic-control" target="|Custom"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Actinic Control</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/anti-pigment"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >anti pigment</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/aquaphor"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Aquaphor Protect &amp; Repair</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/aquaporin-active"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Aquaporin Active</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/atopicontrol"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >AtopiControl</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/deodorants-und-anti-transpirants"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >deodorants and antiperspirants</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/dermato-clean"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >DermatoCLEAN</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/dermocapillaire"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >DermoCapillaire</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/dermo-pure"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >DermoPure</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/hyaluron-filler"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Hyaluron-Filler + 3x EFFECT</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/hyaluron-filler-elasticity"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Hyaluron-Filler + Elasticity</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/hyaluron-filler-urea"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Hyaluron filler + urea</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/hyaluron-filler-volume-lift"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Hyaluron filler + volume lift</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/lipo-balance"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Lipo balance</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/ph5"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >pH5</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/q10-active"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Q10 Active</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/sonnenschutz"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >sun protection</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/urea-repair"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >UreaRepair</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/sehr-empfindliche-haut"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Ultra Sensitive</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >all products</font
                                ></font
                              ></a
                            >
                          </li>
                        </ul>
                      </div>
                    </div>
                  </li>
                  <li class="menu-aim__item">
                    <a href="/produkte"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >skin condition</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    >
                      <div class="cp-third-level-nav-content">
                        <ul class="cp-third-level-nav">
                          <li>
                            <a href="/produkte/anti-age"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >anti age</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/trockene-haut"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Dry skin</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/neurodermitis"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >neurodermatitis</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/juckende-haut"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >itchy skin</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/unreine-haut"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Blemished skin</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/roetungen-im-gesicht"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >reddening of the face</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/empfindliche-haut"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Sensitive skin</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/kopfhaut-und-haarprobleme"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >scalp and hair</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/sonnenschutz"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >sun protection</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a
                              href="/produkte/pigmentflecken-hyperpigmentierung"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Pigment spots &amp; hyperpigmentation</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/schwitzen"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Sweat</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte/diabetische-haut"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >diabetic skin</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/produkte"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >all products</font
                                ></font
                              ></a
                            >
                          </li>
                        </ul>
                      </div>
                    </div>
                  </li>
                </ul>
              </div>
            </li>
            <li class="">
              <a href="/hautzustand" class=""
                ><font style="vertical-align: inherit"
                  ><font style="vertical-align: inherit">Advice</font></font
                ></a
              >

              <div
                class="uk-navbar-dropdown cp-second-level-nav-wrapper uk-navbar-dropdown-dropbar uk-navbar-dropdown-stack uk-navbar-dropdown-bottom-left"
              >
                <ul class="uk-nav uk-navbar-dropdown-nav cp-second-level-nav">
                  <li class="menu-aim__item">
                    <a href="/hautzustand"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >skin condition</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    >
                      <div class="cp-third-level-nav-content">
                        <ul class="cp-third-level-nav">
                          <li>
                            <a href="/hautzustand/anti-age"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >anti age</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/hautzustand/trockene-haut"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Dry skin</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/hautzustand/neurodermitis"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >neurodermatitis</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/hautzustand/unreine-haut"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Blemished skin</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/hautzustand/roetungen-im-gesicht"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >reddening of the face</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/hautzustand/empfindliche-haut"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Sensitive skin</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/hautzustand/sonnenschutz"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >sun protection</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a
                              href="/hautzustand/pigmentflecken-hyperpigmentierung"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Pigment spots &amp; hyperpigmentation</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/hautzustand/schwitzen"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Sweating &amp; deodorant intolerance</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/hautzustand/diabetische-haut"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >diabetic skin</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/hautzustand"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >all articles</font
                                ></font
                              ></a
                            >
                          </li>
                        </ul>
                      </div>
                    </div>
                  </li>
                  <li class="menu-aim__item">
                    <a href="/beratung"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >useful information</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    >
                      <div class="cp-third-level-nav-content">
                        <ul class="cp-third-level-nav">
                          <li>
                            <a href="/beratung/die-haut-grundlagen"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >skin knowledge</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/beratung/hautbehandlung"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >skin care</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/beratung/hautprobleme"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >skin indications</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a href="/hautzustand"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >all articles</font
                                ></font
                              ></a
                            >
                          </li>
                        </ul>
                      </div>
                    </div>
                  </li>
                </ul>
              </div>
            </li>
            <li>
              <a href="/unsere-forschung/aus-der-forschung"
                ><font style="vertical-align: inherit"
                  ><font style="vertical-align: inherit">Research</font></font
                ></a
              >

              <div class="uk-navbar-dropdown cp-second-level-nav-wrapper">
                <ul class="uk-nav uk-navbar-dropdown-nav cp-second-level-nav">
                  <li class="menu-aim__item no-subnav">
                    <a
                      href="/unsere-forschung/aus-der-forschung"
                      target="|Custom"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >Science behind the product lines</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a
                      href="/unsere-forschung/forschungshintergrund"
                      target="|Custom"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >About our research</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/unsere-forschung/datenbank-fuer-inhaltsstoffe"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >Our ingredients</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                </ul>
              </div>
            </li>
            <li>
              <a href="/ueber-eucerin/purpose"
                ><font style="vertical-align: inherit"
                  ><font style="vertical-align: inherit"
                    >Brand &amp; More</font
                  ></font
                ></a
              >

              <div class="uk-navbar-dropdown cp-second-level-nav-wrapper">
                <ul class="uk-nav uk-navbar-dropdown-nav cp-second-level-nav">
                  <li class="menu-aim__item no-subnav">
                    <a href="/ueber-eucerin/purpose"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >Eucerin's purpose</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/anti-age-refill"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >Anti-aging refill capsules</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/koerperpflege-bei-trockener-haut"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >Body care for dry skin</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/muttertag"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >mothers day promo</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/uncover-antipigment"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >#1 against pigment spots</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/dermopure"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >#MYSKINNOFILTER</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/hyfi-gold-relaunch"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >HYALURON-FILLER + ELASTICITY with a new formula</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/aquaphor"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >Aquaphor Protect &amp; Repair</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/hautkrebs-vorsorge-sonnenschutz"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >skin cancer prevention</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/urearepair-hautvertrauen"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >UreaRepair skin trust</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/neurodermitis-atopicontrol"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >Atopic dermatitis care</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/socialmission"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >social mission</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/generationeucerin"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >#generationEucerin</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/frauenstudie"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >women study</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/digitale-hautarzt-diagnose"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >Dermanostic</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a
                      href="/meta-pages/eucerin-treuekarte"
                      target="_blank"
                      rel="noopener noreferrer"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >loyalty program</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/specials/anton"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >Anton</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                </ul>
              </div>
            </li>
            <li class="">
              <a href="/nachhaltigkeit" class=""
                ><font style="vertical-align: inherit"
                  ><font style="vertical-align: inherit"
                    >sustainability</font
                  ></font
                ></a
              >

              <div
                class="uk-navbar-dropdown cp-second-level-nav-wrapper uk-navbar-dropdown-dropbar uk-navbar-dropdown-stack uk-navbar-dropdown-bottom-left"
              >
                <ul class="uk-nav uk-navbar-dropdown-nav cp-second-level-nav">
                  <li class="menu-aim__item">
                    <a href="/nachhaltigkeit/co2-reduzierung"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >CO2 reduction</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    >
                      <div class="cp-third-level-nav-content">
                        <ul class="cp-third-level-nav">
                          <li>
                            <a
                              href="/nachhaltigkeit/co2-reduzierung/nachhaltige-verpackung"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Sustainable packaging</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a
                              href="/nachhaltigkeit/co2-reduzierung/klimaschutz"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >climate protection</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a
                              href="/nachhaltigkeit/co2-reduzierung/nachhaltige-produktion"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >sustainable production</font
                                ></font
                              ></a
                            >
                          </li>
                        </ul>
                      </div>
                    </div>
                  </li>
                  <li class="menu-aim__item">
                    <a href="/nachhaltigkeit/hochwertige-inhaltsstoffe"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >High quality ingredients</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    >
                      <div class="cp-third-level-nav-content">
                        <ul class="cp-third-level-nav">
                          <li>
                            <a
                              href="/nachhaltigkeit/hochwertige-inhaltsstoffe/nachhaltiger-palmoel-anbau"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Sustainable palm oil cultivation</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a
                              href="/nachhaltigkeit/hochwertige-inhaltsstoffe/kosmetik-ohne-tierversuche"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Cosmetics without animal testing</font
                                ></font
                              ></a
                            >
                          </li>
                          <li>
                            <a
                              href="/nachhaltigkeit/hochwertige-inhaltsstoffe/kosmetik-ohne-mikroplastik"
                              ><font style="vertical-align: inherit"
                                ><font style="vertical-align: inherit"
                                  >Cosmetics without microplastics</font
                                ></font
                              ></a
                            >
                          </li>
                        </ul>
                      </div>
                    </div>
                  </li>
                  <li class="menu-aim__item no-subnav">
                    <a href="/nachhaltigkeit/soziale-eingliederung"
                      ><font style="vertical-align: inherit"
                        ><font style="vertical-align: inherit"
                          >Social responsibility</font
                        ></font
                      ></a
                    >

                    <div
                      class="cp-third-level-nav-wrapper menu-aim__item-submenu"
                    ></div>
                  </li>
                </ul>
              </div>
            </li>
          </ul>
        </nav>

        <div class="right-block">
          <span class="pta--deparatment">
            <a href="https://www.side-by-side.de/"> PTA department</a></span
          >

          <span class="pta--flag"
            ><img
              src="../../assets/images/selector-de.png"
              alt="block__item--flag"
              width="20px"
              height="20px"
            />
          </span>
          <span class="pta-language">EN</span>

          <span class="pta--search">
            <svg
              version="1.1"
              xmlns="http://www.w3.org/2000/svg"
              width="25"
              height="25"
              viewBox="0 0 32 32"
            >
              <path
                d="M13.455 2.182c6.226 0 11.273 5.047 11.273 11.273 0 2.851-1.058 5.454-2.803 7.439l7.483 7.485-1.029 1.029-7.485-7.483c-1.985 1.745-4.588 2.803-7.439 2.803-6.226 0-11.273-5.047-11.273-11.273s5.047-11.273 11.273-11.273zM13.455 3.636c-5.422 0-9.818 4.396-9.818 9.818s4.396 9.818 9.818 9.818c5.422 0 9.818-4.396 9.818-9.818s-4.396-9.818-9.818-9.818z"
              ></path>
            </svg>
          </span>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  components: {},
  data() {
    return {
      menuItems: [
        {
          label: "Menu Item 1",
          children: [
            {
              label: "Submenu Item 1",
              children: [
                {
                  label: "Nested Submenu Item 1",
                },
                {
                  label: "Nested Submenu Item 2",
                },
                {
                  label: "Nested Submenu Item 3",
                },
                {
                  label: "Nested Submenu Item 4",
                },
              ],
            },
            {
              label: "Submenu Item 2",
              children: [
                {
                  label: "Nested Submenu Item 3",
                },
                {
                  label: "Nested Submenu Item 4",
                },
              ],
            },
            {
              label: "test",
            },
            {
              label: "test",
            },
          ],
        },
        {
          label: "Menu Item 2",
          children: [
            {
              label: "Submenu Item 2",
              children: [
                {
                  label: "Nested Submenu Item 3",
                },
                {
                  label: "Nested Submenu Item 4",
                },
                {
                  label: "Nested Submenu Item 3",
                },
                {
                  label: "Nested Submenu Item 4",
                },
              ],
            },
          ],
        },
      ],
    };
  },

  methods: {
    showSubmenu(submenuId) {
      const submenu = document.getElementById(submenuId);
      // Get the height of a single list item
      const itemHeight = submenu.querySelector("li").offsetHeight;
      // Get the number of list items in the submenu
      const numItems = submenu.querySelectorAll("li").length;
      // Calculate the height of the submenu
      const submenuHeight = numItems * itemHeight;
      // Set the height of the submenu
      //submenu.style.height = `${submenuHeight}px`; //Hiqe komentin
      // Display the submenu
      //submenu.style.display = "block";
    },

    hideSubmenu(submenuId) {
      document.getElementById(submenuId).style.display = "none";
    },
    showSubSubmenu(submenuId, childIndex) {
      const subsubmenu = document.getElementById(
        `nested-submenu-${submenuId}-${childIndex}`
      );

      subsubmenu.style.display = "block";
    },

    hideSubSubmenu(submenuId, childIndex) {
      // Get the sub-submenu element
      const subsubmenu = document.getElementById(
        `nested-submenu-${submenuId}-${childIndex}`
      );
      // Hide the sub-submenu
      subsubmenu.style.display = "none";
    },
  },
};
</script>

<style scoped lang="scss">
@import "../../assets/scss/layout/header";

/* Start to style na-menu for mobile */

.navbar-first-level__flyout {
  display: none;
}

.navbar-first-level__flyout {
  background-color: #e8eaeb;
  width: 100%;
  /*display: flex;
  flex-direction: column;
  justify-content: space-between;*/
  align-items: stretch;
  left: 0;
  position: absolute;

  & li {
    /* display: flex;*/
    list-style: none;
  }
}

/* Add this CSS rule to hide the submenus by default */
.navbar-first-level__flyout.submenu {
  display: none;
}

ul {
  display: flex;
  justify-content: center;
  align-items: center;

  & li {
    list-style: none;
  }

  & a {
    color: $textcolor;
    display: block;
    padding: 10px 5px;
    text-decoration: none;
    text-decoration: none;
    font-size: 1.6rem;
    line-height: 1.9rem;
    margin: 0 13px;
  }
}

/* Use the :hover pseudo-class to show the submenu when hovering over the main menu item */
ul .navbar-first-level__item:hover .navbar-first-level__flyout.submenu {
  display: block;
}

ul .submenu li .arrow-right::after {
  border: solid $danger;
  border-width: 0 2px 2px 0;
  display: inline-block;
  padding: 3px;
  content: "";
  transform: rotate(-45deg);
  -webkit-transform: rotate(-45deg);
}

.nested-submenu {
  display: none;
}
.navbar-secondary-level__item:hover .nested-submenu {
  display: block;
}
</style>
