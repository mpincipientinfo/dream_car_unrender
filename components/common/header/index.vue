<template>
  <div class="d-flex justify-content-center">
    <div class="bv-example-row position-absolute header">
      <b-row class="m-0">
        <b-col sm="3">
          <b-img style="margin-top:6px" :src="imgUrl"> </b-img>
        </b-col>
        <b-col
          sm="9"
          align-v="center"
          class="d-flex justify-content-end align-self-center"
        >
          <b-list-group horizontal>
            <nuxt-link
              to="#"
              class="hover-text-decoration-none d-flex align-self-center"
              v-for="(navBar, index) in navBarList"
              :key="index"
            >
              <b-list-group-item class="bg-transparent border-0 text-uppercase">
                {{ navBar.title }}
              </b-list-group-item>
            </nuxt-link>
            <nuxt-link to="#" class="hover-text-decoration-none">
              <b-list-group-item class="bg-transparent border-0">
                <b-button class="btn-red">{{ navBarButton }}</b-button>
              </b-list-group-item>
            </nuxt-link>
          </b-list-group>
        </b-col>
      </b-row>
    </div>
  </div>
</template>
<script>
export default {
  props: ["headerDataProp"],
  data() {
    return {
      imgUrl: this.headerDataProp.imgUrl,
      navBarList: this.headerDataProp.navBarList,
      navBarButton: this.headerDataProp.navBarButton
    };
  },
  watch: {
    headerDataProp: {
      deep: true,
      handler(newVal, oldVal) {
        this.imgUrl = newVal.imgUrl;
        this.navBarList = newVal.navBarList;
        this.navBarButton = newVal.navBarButton;
      }
    }
  }
};
</script>
<style scoped>
.list-group a.hover-text-decoration-none.d-flex.align-self-center{
    padding-left: 25px;
    padding-right: 25px;
    font-family: Open Sans,sans-serif!important;
    font-size: 1.0625rem;
    font-weight: 500!important;
    padding-top: 0!important;
    padding-bottom: 0!important;
    color: #fff!important;
    }
 .list-group .list-group-item.text-uppercase{
    font-size: 17px;
    font-weight: 500;
    line-height: 26px;
    padding-right: .5rem;
    padding-left: .5rem;
}
.w-100 {
    padding-top: 40px;
}
 .list-group .list-group-item{
    padding: 0.75rem 0rem;
}
 .justify-content-lg-start, .justify-content-lg-end{
	padding:0px
}
.header {
  width: 100%;
  padding: 0 7% 7px;
  border-bottom: 1px solid hsla(0, 0%, 100%, 0.5);
  top: 22px;
  z-index: 1;
}
.list-group-item {
  color: hsla(0, 0%, 100%, 0.5);
}
.list-group-item:hover {
  color: hsla(0, 0%, 100%, 0.75);
}
</style>
