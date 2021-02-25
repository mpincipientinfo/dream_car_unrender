<template>
  <div>
    <SectionHead :sectionHeadDataProp="sectionHeadData" />
    <SectionReferences :sectionReferenceDataProp="sectionReferenceDataProp" />
    <SectionBenefits :sectionBenefitDataProp="sectionBenefitData" />
    <SectionServices :servicesProp="services" />
    <SectionContact :sectionContactDataProp="sectionContactDataProp" />
  </div>
</template>
<script>
import params from "@/config/params.js";
import SectionHead from "./sections/section_head";
import SectionBenefits from "./sections/section_benefits";
import SectionServices from "./sections/section_services";
import SectionContact from "./sections/section_contact";
import SectionReferences from "./sections/section_references";
export default {
  components: {
    SectionHead,
    SectionBenefits,
    SectionServices,
    SectionContact,
    SectionReferences
  },
  data() {
    return {
      sectionHeadData: {},
      sectionBenefitData: {},
      services: {},
      sectionContactDataProp: {},
      sectionReferenceDataProp: {}
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const { data } = await this.$axios.get(
        params.baseUrl + "/payload/home.json"
      );
      this.sectionHeadData = {
        backgroundImageUrl: data.section_head.background_image.url,
        imageUrl: data.section_head.image.url,
        title: data.section_head.title,
        subtitle: data.section_head.subtitle,
        button1: data.section_head.button_1,
        button2: data.section_head.button_2
      };
      this.sectionBenefitData = data.section_vorteile;
      this.services = data.section_services;
      this.sectionContactDataProp = {
        backgroundImageUrl: data.section_contact.background_image.url,
        title: data.section_contact.title,
        description: data.section_contact.description,
        button: data.section_contact.button
      };
      this.sectionReferenceDataProp = data.section_referenzen;
    }
  }
};
</script>
