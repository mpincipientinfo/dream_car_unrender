<template>
  <div class="mt-3 mb-3">
    <div class="carousel-wrapper">
      <div>
        <client-only>
          <splide :options="options">
            <splide-slide>
              <img src="https://source.unsplash.com/random" /> </splide-slide
            ><splide-slide>
              <img src="https://source.unsplash.com/random" /> </splide-slide
            ><splide-slide>
              <img src="https://source.unsplash.com/random" /> </splide-slide
            ><splide-slide>
              <img src="https://source.unsplash.com/random" />
            </splide-slide>
          </splide>
        </client-only>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["sectionReferenceDataProp"],
  data() {
    return {
      options: {
        infinite: true,
        type: "loop",
        perPage: 3,
        dots: false,
        perMove: 1,
        pagination: false,
        height: "400px",
        width: "auto"
      }
    };
  },
  mounted() {

  }
};
</script>
