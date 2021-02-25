<template>
  <div>
    <div
      class="d-flex align-items-center justify-content-center justify-content-md-start"
    >
      <h4 class="count">{{ benefitCount }}</h4>
      <div class="ml-2">
        <b-img :src="benefit.image.url"></b-img>
      </div>
    </div>
    <h6 class="title pt-4">{{ benefit.title }}</h6>
    <p class="description pt-4">{{ benefit.description }}</p>
  </div>
</template>
<script>
export default {
  props: ["benefitProp", "benefitCountProp"],
  data() {
    return {
      benefit: this.benefitProp,
      benefitCount: this.benefitCountProp
    };
  }
};
</script>
<style scoped>
.title {
  font-family: Lora, serif !important;
  font-size: 1.725rem;
  font-weight: 500;
  color: #fff;
  line-height: 1.5;
}
.description {
  font-size: 1.0835rem;
  color: #fff;
  line-height: 2;
}
.count {
  font-family: Open Sans, sans-serif !important;
  font-size: 5rem;
  font-weight: 600;
  color: hsla(0, 0%, 100%, 0.16);
}
.description{
    font-family: Open Sans,sans-serif!important;
    font-size: 1.0625rem;
    color: #fff;
    line-height: 2;
    padding-top: 26px;
}
.title[data-v-76389483]{
    font-size: 26px;
    font-weight: 500;
    color: #fff;
    padding-top: 20px !important;
    line-height: 39px;
  }
</style>
