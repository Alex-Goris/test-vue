<template>
  <div>
    <slick
            ref="slick"
            :options="slickOptions"
            @afterChange="handleAfterChange"
            @beforeChange="handleBeforeChange"
            @breakpoint="handleBreakpoint"
            @destroy="handleDestroy"
            @edge="handleEdge"
            @init="handleInit"
            @reInit="handleReInit"
            @setPosition="handleSetPosition"
            @swipe="handleSwipe"
            @lazyLoaded="handleLazyLoaded"
            @lazyLoadError="handleLazeLoadError">
      <a :href="image.url" v-for="image in images">
        <img :src="image.url" alt="">
      </a>

    </slick>

  </div>
</template>

<script>

  import Slick from 'vue-slick'
  export default {
    components: { Slick },

    data() {
      return {
        images: [
          {url: 'http://placehold.it/370x200'},
          {url: 'http://placehold.it/370x200'},
          {url: 'http://placehold.it/370x200'},
          {url: 'http://placehold.it/370x200'},
          {url: 'http://placehold.it/370x200'},
          {url: 'http://placehold.it/370x200'}
        ],
        slickOptions: {
          slidesToShow: 3,
          slidesToScroll: 3,

          speed: 300,
          responsive: [
            {
              breakpoint: 1024,
              settings: {
                slidesToShow: 3,
                slidesToScroll: 3,
                infinite: true,
                dots: true
              }
            },
            {
              breakpoint: 600,
              settings: {
                slidesToShow: 2,
                slidesToScroll: 2
              }
            },
            {
              breakpoint: 480,
              settings: {
                slidesToShow: 1,
                slidesToScroll: 1
              }
            }
            // You can unslick at a given breakpoint now by adding:
            // settings: "unslick"
            // instead of a settings object
          ]
          // Any other options that can be got from plugin documentation
        },
      };
    },

    // All slick methods can be used too, example here
    methods: {
      next() {
        this.$refs.slick.next();
      },

      prev() {
        this.$refs.slick.prev();
      },

      reInit() {
        // Helpful if you have to deal with v-for to update dynamic lists
        this.$nextTick(() => {
          this.$refs.slick.reSlick();
        });
      },

      // Events listeners
      handleAfterChange(event, slick, currentSlide) {
        console.log('handleAfterChange', event, slick, currentSlide);
      },
      handleBeforeChange(event, slick, currentSlide, nextSlide) {
        console.log('handleBeforeChange', event, slick, currentSlide, nextSlide);
      },
      handleBreakpoint(event, slick, breakpoint) {
        console.log('handleBreakpoint', event, slick, breakpoint);
      },
      handleDestroy(event, slick) {
        console.log('handleDestroy', event, slick);
      },
      handleEdge(event, slick, direction) {
        console.log('handleEdge', event, slick, direction);
      },
      handleInit(event, slick) {
        console.log('handleInit', event, slick);
      },
      handleReInit(event, slick) {
        console.log('handleReInit', event, slick);
      },
      handleSetPosition(event, slick) {
        console.log('handleSetPosition', event, slick);
      },
      handleSwipe(event, slick, direction) {
        console.log('handleSwipe', event, slick, direction);
      },
      handleLazyLoaded(event, slick, image, imageSource) {
        console.log('handleLazyLoaded', event, slick, image, imageSource);
      },
      handleLazeLoadError(event, slick, image, imageSource) {
        console.log('handleLazeLoadError', event, slick, image, imageSource);
      },
    }
  }
</script>

<style>
  .slick-arrow {
    color: #fff;
    background-color: #6c757d;
    border-color: #6c757d;
    margin: 1rem;
    display: inline-block;
    font-weight: 400;
    text-align: center;
    white-space: nowrap;
    vertical-align: middle;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    border: 1px solid transparent;
    padding: 0.375rem 0.75rem;
    font-size: 1rem;
    line-height: 1.5;
    border-radius: 0.25rem;
  }
  img {
    border: 2px solid #fff;

  }
</style>
