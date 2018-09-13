
<template>
<div class="banner" :style=calHeight>
    <div class="header-row common-banner-fix" id="header-row" :style=style>
   <div class="container  container-table">
   <div class="vertical-center-row">
      <div class="row  justify-content-end">     
            <div class="col-lg-6 col-lg-offset-6">
                <h1 class="common-banner-head">{{banner.data.heading}}</h1>
                <h3>{{banner.data.body}}</h3>
            </div>
         </div>
      </div>
   </div>
</div>
</div>
</template>

<script>
export default {
    props:{
        banner:{
            type: Object,
            required: true
        }
    },
    computed: {
      style () {
        return 'backgroundImage: url( "' + this.banner.url + '")';
      },
      calHeight(){
          return 'height:'+ (window.innerHeight) +'px';
      }
    }
}
</script>

