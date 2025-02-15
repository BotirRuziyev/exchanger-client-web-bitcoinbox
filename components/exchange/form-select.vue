<template>
  <div class="form-select" ref="selectRef">
    <div class="select-btn" @click="isSelect = !isSelect">
      <div class="select-name">
        <div class="coin-name">{{ coinName }}</div>
        <span class="token-standard">{{ tokenStandard }}</span>
      </div>
      <div class="coin-img">
        <img :src="coinImg" :alt="coinName" />
      </div>
      <div class="select-arrown">
        <img src="~assets/img/icons/arrow-down.svg" alt="" />
      </div>
    </div>
    <div class="select-menu" :class="isSelect ? 'open-menu' : ''">
      <div
        class="select-option"
        v-for="coin of coinsList"
        :key="coin.id"
        @click="changeSelect(coin)"
      >
        <div class="coin-img">
          <img :src="coin.img" alt="" />
        </div>
        <div class="select-name">
          <div class="coin-name">{{ coin.coinName }}</div>
          <span>{{ coin.tokenStandard }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isSelect: {
      typeof: Boolean,
      default: false,
    },
    coinName: {
      typeof: String,
      default: "",
    },
    tokenStandard: {
      typeof: String,
      default: "",
    },
    coinImg: {
      typeof: String,
      default: "",
    },
    coinsList: Array,
  },
  mounted() {
    document.addEventListener("click", this.closeOnClickOutside);
  },
  beforeUnmount() {
    document.removeEventListener("click", this.closeOnClickOutside);
  },
  methods: {
    changeSelect(coin) {
      this.coinName = coin.coinName;
      this.tokenStandard = coin.tokenStandard;
      this.coinImg = coin.img;
      this.isSelect = false;
    },
    closeOnClickOutside(event) {
      if (!this.$refs.selectRef.contains(event.target)) {
        this.isSelect = false;
      }
    },
  },
};
</script>
