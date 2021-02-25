<template>
  <div>
    <Header :headerDataProp="headerData" />
    <Nuxt />
    <Footer :footerDataProp="footerData" />
  </div>
</template>
<script>
import params from "@/config/params.js";
import Header from "@/components/common/header";
import Footer from "@/components/common/footer";
export default {
  components: {
    Header,
    Footer
  },
  data() {
    return {
      headerData: {},
      footerData: {}
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const { data } = await this.$axios.get(
        params.baseUrl + "/payload/shared.json"
      );
      this.headerData = {
        imgUrl: data.section_navbar.image.url,
        navBarList: data.section_navbar.image.page_links,
        navBarButton: data.section_navbar.image.button
      };
      this.footerData = {
        imgUrl: data.section_footer.image.url,
        title: data.section_footer.title,
        pageLinks: data.section_footer.page_links,
        legalLinks: data.section_footer.legal_links
      };
    }
  }
};
</script>
