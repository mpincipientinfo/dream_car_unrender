<template>
  <div>
    <!-- main section -->
    <div class="footer">
      <div class="d-flex flex-column">
        <div class="home__logo text-center">
          <div class="text-center">
            <div class="mb-3">
              <img alt="" class="img-fluid lazyLoad isLoaded" :src="imgUrl" />
            </div>
            <div>
              <img src="@/assets/images/logoline.f940fa9.png" alt="Image" />
            </div>
            <p class="title mt-3 pt-1 mb-3">{{ title }}</p>
            <!-- page links -->
            <div class="pt-40">
              <div
                align-v="center"
                class="d-flex justify-content-center align-self-center"
              >
                <div class="list-group list-group-horizontal">
                  <a
                    href="/#"
                    class="btn d-flex align-self-center link text-uppercase"
                    v-for="(pageLink, index) in pageLinks"
                    :key="index"
                  >
                    <div class="list-group-item bg-transparent border-0">
                      {{ pageLink.title }}
                    </div>
                  </a>
                </div>
              </div>
            </div>
            <!-- //legal links -->
            <div>
              <div
                align-v="center"
                class="d-flex justify-content-center align-self-center"
              >
                <div class="list-group list-group-horizontal">
                  <a
                    href="/#"
                    class="btn d-flex align-self-center link"
                    v-for="(legalLink, index) in legalLinks"
                    :key="index"
                  >
                    <div class="list-group-item bg-transparent border-0 p-0">
                      {{ legalLink.title }}
                    </div>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- social div -->
    <div class="social_parent">
      <div class="container">
        <b-row>
          <div class="col-lg-4 text-center">
            <a href="tel:+436763893322" class="social_meta">
              <img
                src="https://admin.m2-wunschauto.at/wp-content/uploads/2021/02/phone-call.png"
              />
              <p class="mt-3">0676 38 93 322</p>
            </a>
          </div>
          <div class="col-lg-4 text-center">
            <a href="mailto:office@m2-wunschauto.at" class="social_meta">
              <img
                src="https://admin.m2-wunschauto.at/wp-content/uploads/2021/02/email.png"
              />
              <p class="mt-3">office@m2-wunschauto.at</p>
            </a>
          </div>
          <div class="col-lg-4 text-center">
            <a
              target="_blank"
              href="https://www.instagram.com/m2.wunschauto/"
              class="social_meta"
            >
              <img
                src="https://admin.m2-wunschauto.at/wp-content/uploads/2021/02/instagram.png"
              />
              <p class="mt-3">Instagram</p>
            </a>
          </div>
        </b-row>
      </div>
    </div>
    <!-- copyright -->
    <div class="copyright text-center">
      <h6 class="copyright_text">
        ©copyright 2021 M2-wunschauto . All Rights Reserved
      </h6>
    </div>
  </div>
</template>
<script>
export default {
  props: ["footerDataProp"],
  data() {
    return {
      imgUrl: this.footerDataProp.imgUrl,
      title: this.footerDataProp.title,
      pageLinks: this.footerDataProp.pageLinks,
      legalLinks: this.footerDataProp.legalLinks
    };
  },
  watch: {
    footerDataProp: {
      deep: true,
      handler(newVal, olVal) {
        this.imgUrl = newVal.imgUrl;
        this.title = newVal.title;
        this.pageLinks = newVal.pageLinks;
        this.legalLinks = newVal.legalLinks;
      }
    }
  }
};
</script>
<style scoped>
.title {
  color: #182540;
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
}
.link {
  font-family: Open Sans, sans-serif !important;
  font-weight: 600;
  color: #182540;
}
.social_parent {
  background: #f8f9fa;
  padding-top: 4rem;
  padding-bottom: 3rem;
}
.social_meta:hover,
.social_meta {
  color: #030508;
  text-decoration: none;
}
.copyright_text {
  font-family: Open Sans, sans-serif !important;
  font-size: 0.875rem;
  color: #fff;
  margin-bottom:0px;
}
.copyright {
  background-color: #182540;
    padding-top: 11px;
    padding-bottom: 10px;
}
.pt-40{
	padding-top:40px;
	padding-bottom:12px;
}
.footer a{
	padding:0px!important;
}
.footer{
	padding:100px 0px;
}
.footer .list-group-item{
	padding:0px 25px !important;
	font-size:17px;
}
</style>
