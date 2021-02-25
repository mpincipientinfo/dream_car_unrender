<template>
  <div>
    <div
      class="background_image"
      :style="{ backgroundImage: `url(${backgroundImageUrl})` }"
    >
      <div
        class="d-flex flex-column align-items-center justify-content-center h-100"
      >
        <b-img :src="imageUrl"></b-img>
        <h1 class="text-light title">
          <i>
            {{ title }}
          </i>
        </h1>
        <h2 class="subtitle text-light">{{ subtitle }}</h2>
        <b-row class="w-100 pt-4">
          <b-col
            lg="6"
            md="12"
            class=" justify-content-lg-end justify-content-center d-flex"
          >
            <a href="#" class="btn-red btn text-uppercase">{{ button1 }}</a>
          </b-col>
          <b-col
            lg="6"
            md="12"
            class=" justify-content-lg-start justify-content-center d-md-flex d-none"
          >
            <a href="#" class="btn-blue btn text-uppercase">{{ button2 }}</a>
          </b-col>
        </b-row>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["sectionHeadDataProp"],
  data() {
    return {
      backgroundImageUrl: this.sectionHeadDataProp.backgroundImageUrl,
      imageUrl: this.sectionHeadDataProp.imageUrl,
      title: this.sectionHeadDataProp.title,
      subtitle: this.sectionHeadDataProp.subtitle,
      button1: this.sectionHeadDataProp.button1,
      button2: this.sectionHeadDataProp.button2
    };
  },
  watch: {
    sectionHeadDataProp: {
      deep: true,
      handler(newVal, oldval) {
        this.backgroundImageUrl = newVal.backgroundImageUrl;
        this.imageUrl = newVal.imageUrl;
        this.title = newVal.title;
        this.subtitle = newVal.subtitle;
        this.button1 = newVal.button1;
        this.button2 = newVal.button2;
      }
    }
  }
};
</script>
<style scoped>
.justify-content-lg-start{
	padding-left:5px
}
.justify-content-lg-end{
	padding-right:25px
}
.h-100 .w-100{
	padding-top:40px!important;
}
.background_image {
  height: 800px;
}
.title {
  font-family: Open Sans, sans-serif !important;
  font-size: 2.3125rem;
  padding-top: 27px;
  letter-spacing:1px;
}
.subtitle {
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
}
</style>
