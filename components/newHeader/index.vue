<template>
  <header class="header">
    <div class="header-container">
      <div class="logo">
        <nuxt-link :to="localePath(`/`)">
          <img src="~assets/img/logo.svg" alt="" />
        </nuxt-link>
      </div>
      <div class="border-left"></div>
      <nav class="header-nav">
        <div class="nav-link__group">
          <div class="link-item">
            <nuxt-link :to="localePath(`/exchange/`)" class="nav-link">
              <span></span>
              Обмен
            </nuxt-link>
          </div>
          <div class="link-item">
            <nuxt-link to="#" class="nav-link">
              <span></span>
              Преимущества
            </nuxt-link>
          </div>
          <div class="link-item">
            <nuxt-link to="#" class="nav-link">
              <span></span>
              Контакты
            </nuxt-link>
          </div>
        </div>
        <div class="header-right__block">
          <div class="dropdown-lang" ref="langRef">
            <div class="inner_dropdown" @click="isShow = !isShow">
              <div class="dropdown-lang-inner-name">
                {{ langName }}
              </div>
              <div class="dropdown-lang-img-arrow">
                <img src="~/assets/img/icons/arrow-down.svg" />
              </div>
            </div>
            <ul v-if="isShow" class="lang-menu">
              <li v-for="locale in $i18n.locales" :key="locale.code">
                <nuxt-link
                  :to="switchLocalePath(locale.code)"
                  @click.prevent.stop="$i18n.setLocale(locale.code)"
                  :class="{
                    'active-lang-link': locale.code === lang,
                    pointer: true,
                  }"
                >
                  <div @click="isShow = false" class="dropdown-lang-inner-img">
                    <div v-if="locale.code === 'ru'">
                      <img src="~/assets/img/flag/ru.svg" />
                      <span>{{ locale.name }}</span>
                    </div>
                    <div
                      v-else-if="locale.code === 'ua' || locale.code === 'uk'"
                    >
                      <img src="~/assets/img/flag/uk.svg" />
                      <span>{{ locale.name }}</span>
                    </div>
                    <div v-else-if="locale.code === 'en'">
                      <img src="~/assets/img/flag/en.svg" />
                      <span>{{ locale.name }}</span>
                    </div>
                    <div v-else-if="locale.code === 'pl'">
                      <img src="~/assets/img/flag/pl.svg" />
                      <span>{{ locale.name }}</span>
                    </div>
                    <div v-else-if="locale.code === 'es'">
                      <img src="~/assets/img/flag/es.svg" />
                      <span>{{ locale.name }}</span>
                    </div>
                    <div v-else>
                      <span>[Lang]</span>
                    </div>
                  </div>
                </nuxt-link>
              </li>
            </ul>
          </div>
          <div class="border-left"></div>
          <logo-sign />
        </div>
      </nav>
    </div>
  </header>
</template>

<script>
import { mapActions, mapGetters, mapMutations } from "vuex";
import logoSign from "~/components/header/logosign";

export default {
  data: () => {
    return {
      isShow: false,
    };
  },
  components: {
    logoSign,
  },

  computed: {
    lang() {
      return this.$i18n.locale;
    },
    langName() {
      if (this.$i18n.locale === "ua" || this.$i18n.locale === "uk") {
        return `${this.$i18n.locale}`;
      } else if (this.$i18n.locale === "eu") {
        return `${this.$i18n.locale}`;
      } else if (this.$i18n.locale === "pl") {
        return `${this.$i18n.locale}`;
      } else if (this.$i18n.locale === "es") {
        return `${this.$i18n.locale}`;
      } else if (this.$i18n.locale === "ru") {
        return "Русский";
      } else {
        return "English";
      }
    },
    // ...mapGetters({
    //   showMenu: "menu/menu",
    //   buttons: "menu/buttons",
    //   link: "rules/getLink",
    // }),
    // ...mapGetters({ favoriteRates: "exchange/favoriteRates" }),
  },
  mounted() {
    document.addEventListener("click", this.closeOnClickOutside);
  },
  beforeUnmount() {
    document.removeEventListener("click", this.closeOnClickOutside);
  },
  methods: {
    closeOnClickOutside(event) {
      if (!this.$refs.langRef.contains(event.target)) {
        this.isShow = false;
      }
    },
  },
  //   created() {
  //     this.favRoutes();
  //     this.getButtons();
  //   },
  //   methods: {
  //     ...mapMutations({ changeMenu: "menu/menu" }),
  //     ...mapActions({
  //       favRoutes: "exchange/favRoutes",
  //       getButtons: "menu/buttons",
  //       menuAllChange: "menu/all",
  //     }),
  //   },
};
</script>
