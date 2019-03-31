<template>
  <div class="container mt-3">
      <div v-for="(company) in getCompany"
            :key="company.id"
        >
         <st-logo-image :logo="company.logo_path" />
        {{ company.name }}
        </div>
                
  </div>
</template>

<script>
  import actions from '../../store/action-types';
  import mutations from '../../store/mutation-types';
  import StLogoImage from './logoImage';

  export default {
    name: 'st-featured',
    created() {
      this.getCompany();
    },
    components: {
        StLogoImage
    },
    computed: {
        getCompany(){
            return this.$store.state.company;
        }
    },    
    methods: {
      getCompany() {
        this.$store.dispatch(actions.GET_COMPANY, {});
      },
    },
  };
</script>
