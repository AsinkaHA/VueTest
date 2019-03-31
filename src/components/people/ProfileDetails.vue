<template>
<div class="container">
  <div class="row">
    <div class="col">
      <div class="card flex-row mt-3 profile-container">
        <st-profile-image :profile="person.profile_path"></st-profile-image>
        <div class="profile-info d-flex flex-column p-3">
          
          
          <div>
            <!-- <i @click="addToFavorite" class="fa fa-star fav-icon" :class="getIsFav"></i> -->
          </div>
          <p class="text-dark"><span>{{ getProfileImage.release_date | moment("MMMM D Y") }}</span>
          <p class="text-black-50 overview-info">{{ getProfileImage.overview }}</p>
        </div>
        </div>
    </div>
  </div>
</div>

</template>

<script>
  import actions from '../../store/action-types';
  import StProfileImage from './profileImage';
  
  export default {
    name: 'st-profile-details',
    created(){
      if(!this.$store.state.profile){
        const personId = this.$route.params.id;
        this.$store.dispatch(actions.GET_PROFILE_DETAILS, personId);
      }
    },
    components: {
      StProfileImage,
     
    },
    computed: {
      getProfile(){
        if(this.$store.state.currentProfile){
          return this.$store.state.Profile
        }
        return {};
      }
    }
  }
</script>