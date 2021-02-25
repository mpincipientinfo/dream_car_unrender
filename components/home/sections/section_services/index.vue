<template>
  <div>
    <b-row v-for="(service, index, count) in services" :key="index" class="m-0">
      <!-- For first record: display image in right, for second record: display image in left & continue same pattern -->
      <!-- image in right -->
      <b-col lg="6" class="d-none d-md-block p-0 " v-if="count % 2 != 0">
        <img :src="service.image.url" class="w-100 fluid image h-100" />
      </b-col>
      <b-col
        lg="6"
        sm="12"
        class="p-0 padd_left_12_per pt-5  col-sm-12 col-lg-6"
      >
        <h2 class="pb-3 title">{{ service.title }}</h2>
        <div v-for="(list, index) in service.list" :key="index">
          <b-img src="@/assets/images/tick.e546d3c.svg" class="float-left">
          </b-img>
          <p class="list_title pb-3 ml-2">{{ list.title }}</p>
        </div>
        <div
          class=" mb-2  d-flex flex-sm-row justify-content-center justify-content-sm-start flex-column w-100 pt-24"
        >
          <div class="w-50">
            <a href="#" class="btn-red button btn btn-red-expand">
              {{ service.button }}
            </a>
          </div>
          <div
            class="d-flex align-items-start flex-column bd-highlight "
            v-if="service.price"
          >
            <div class="bd-highlight">
              <div class="price_tag">
                <b-img src="@/assets/images/price_tag.jpeg"></b-img>
                <p class="price_tag_text">PRIES</p>
              </div>
              <h5 class="price">
                {{ service.price }}
              </h5>
            </div>
          </div>
        </div>
      </b-col>
      <!-- image in left -->
      <b-col lg="6" class="d-none d-md-block p-0 h-652" v-if="count % 2 == 0">
        <img :src="service.image.url" class="w-100 fluid h-100" />
      </b-col>
    </b-row>
  </div>
</template>
<script>
export default {
  props: ["servicesProp"],
  data() {
    return {
      count: 0,
      services: this.servicesProp
    };
  },
  watch: {
    servicesProp: {
      deep: true,
      handler(newVal, oldVal) {
        this.services = newVal;
      }
    }
  }
};
</script>
<style scoped>
.padd_left_12_per{
  padding-left: 64px!important;
  padding-top:80px!important;
  padding-bottom:72px!important;
}
.row.m-0:first-child .padd_left_12_per{
  padding-left: 14.4% !important;
}

.list_title {
    font-size: 1.0625rem;
    color: #182540;
    padding-left: 41px;
    font-family: Open Sans,sans-serif!important;
    font-size: 1.0625rem;
    color: #182540;
    margin-bottom: 0px;
    padding-bottom: 36px!important;
}
.image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  -o-object-fit: cover;
  object-fit: cover;
}
.title {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  color: #182540;
  font-weight: 500;
  padding-bottom: 20px !important;
}
.price_tag {
  position: relative;
}
.price_tag_text {
  position: absolute;
  top: 1px;
  left: 10px;
  color: #fff;
  letter-spacing: 7px;
  font-family: Open Sans, sans-serif !important;
  font-size: 0.875rem;
}
.price {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  font-weight: 500;
  color: #182540;
}
.pt-24{
	padding-top:24px;
}
a.btn-red.button.btn.btn-red-expand {
    border-radius: 60px !important;
    background: linear-gradient(90deg, #e50612, #730309) !important;
    color: #fff !important;
    text-align: center !important;
    padding: 14px 12px 6px 12px;
    border: 0;
    overflow: hidden;
    position: relative;
    z-index: 1;
    font-family: Open Sans, sans-serif !important;
    font-size: 18px;
    line-height: 27px;
    height: 59px;
}
.w-50{
	flex-basis:50%
}
.btn-red-expand:hover {
    transition: all .5s!important;
    width: 262px;
    letter-spacing: 2px;
}
.d-none.d-md-block.p-0.h-652.col-lg-6{
	position:relative;
}
.h-652 img.w-100.fluid.h-100 {
    object-fit: cover;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    -o-object-fit: cover;
    object-fit: cover;
}
.btn-red-expand {
  width: 209px;
}
</style>
