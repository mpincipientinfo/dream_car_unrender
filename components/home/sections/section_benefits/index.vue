<template>
  <div
    class="benefit_parent d-flex flex-column align-items-center justify-content-center"
  >
    <h3 class="subtitle mb-1">{{ subtitle }}</h3>
    <h2 class="title pt-4 pb-6">{{ title }}</h2>
    <b-container class="bv-example-row counter-number">
      <b-row>
        <b-col v-for="(benefit, index) in benefits" :key="index">
          <BenefitComponent
            :benefitProp="benefit"
            :benefitCountProp="index + 1"
          />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import BenefitComponent from "./BenefitComponent";
export default {
  props: ["sectionBenefitDataProp"],
  components: {
    BenefitComponent
  },
  data() {
    return {
      title: this.sectionBenefitDataProp.title,
      subtitle: this.sectionBenefitDataProp.subtitle,
      benefits: this.sectionBenefitDataProp.vorteile
    };
  },
  watch: {
    sectionBenefitDataProp: {
      deep: true,
      handler(newVal, oldval) {
        this.title = newVal.title;
        this.subtitle = newVal.subtitle;
        this.benefits = newVal.vorteile;
      }
    }
  }
};
</script>
<style scoped>
.benefit_parent {
  background-color: #182540;
  color: #fff;
  padding-bottom:80px;
}
.subtitle {
  font-size: 1.125rem;
  font-weight: 600;
  padding-top: 140px;
  font-family: "Mulish", sans-serif;
  margin-bottom:8px !important;
}
 .title {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  padding-bottom: 60px;
  padding-top:20px!important;
}

</style>
