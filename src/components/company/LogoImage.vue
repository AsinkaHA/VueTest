<template>
    <div class="image-container">
      <img :src="getLogoImage" class="Logo-thumbnail"/>
    </div>
</template>

<script>
  import constants from '../../constants';
  export default {
    name: 'st-logo-image',
    props: {
      logo: {
        type: String,
      },
    },
    computed: {
      getLogoImage() {
        const logo = constants.basePosterURL + this.logo;
        return logo;
      },
    },
  };
</script>

<style lang="scss" scoped>
  .logo-thumbnail {
    width: 189px;
  }
</style>
