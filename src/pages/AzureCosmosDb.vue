<template>
    <div class="cosmos common-page-img-fix page-section" id="cosmos">
        <div class="container-fluid common-page-head">
           
            <div class="container">
                <div>
                    <h3>{{cosmosInfo.chapter}}</h3>
                </div>
                <div>
                    <h1>{{cosmosInfo.title}}</h1>
                </div>
                <div class="d-lg-none imageContainer d-xl-none d-md-none">
                    <img v-bind:src="cosmosInfo.urlsm" alt="">
                </div>
            </div> 
        </div>
        <div class="container-fluid common-page-subhead">
            <div class="container">
                <div class="row">
                    <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
                        <h3>{{cosmosInfo.head}}</h3>
                    </div>
                    <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 imageContainer d-sm-none d-none d-md-block d-lg-block d-xl-block">
                        <img v-bind:src="cosmosInfo.url" alt="">
                    </div>
                </div>
                
            </div> 
        </div>
        <div class="container-fluid common-div">
                <div class="container border-bottom-black commonGutSpaceBtm">
                    <div class="row commonGutSpaceBtm">
                        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
                            <p>{{cosmosInfo.textPrimary}}</p>
                            <p v-html="cosmosInfo.textContent">{{cosmosInfo.textContent}}</p>
                            </div>
                        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
                            <p v-html="cosmosInfo.textSecondary">{{cosmosInfo.textSecondary}}</p>
                            </div>
                    </div>
                </div>
                <div class="container">
                    <div class="border-bottom-black common-card-padd common-topBtm-padd">
                        <div>
                            <h3 class="blue">{{cosmosInfo.appData.title}}</h3>
                            <p>{{cosmosInfo.appData.content}}</p>
                        </div>
                        <ul class="nav nav-pills mb-3 nav-fill" id="pills-tab" role="tablist">
                        <li class="nav-item" v-for="(items,index) in cosmosInfo.appData.navData">
                            <a class="nav-link " :class="{ 'active': index === 0 }" v-bind:id="'pills-'+items.content.link+'-tab'" data-toggle="pill" v-bind:href="'#pills-'+items.content.link" role="tab" aria-controls="strong-home" aria-selected="true"><strong>{{items.content.title}}</strong></a>
                        </li>
                    </ul>
                    <div class="tab-content" id="pills-tabContent">
                        <div v-for="(items,index) in cosmosInfo.appData.navData" class="tab-pane fade" v-bind:id="'pills-'+items.content.link" role="tabpanel" aria-labelledby="pills-strong-tab" :class="{ 'active show': index === 0 }">
                            <div class="row">
                                <div class="col-lg-3  col-xs-12 col-sm-12 text-center">
                                    <img v-bind:src="items.content.url" alt="">
                                </div>
                                <div  class="col-lg-9 col-lg-3 col-xs-12 col-sm-12">
                                    <h3 class="blue">{{items.content.head}}</h3>
                                    <p>{{items.content.content.infoPrimary}}</p>
                                    <ul class="">
                                        <li v-for="listData in items.content.content.listData">
                                            <p><span  v-html="listData.title">{{listData.title}}</span> <span>{{listData.content}}</span></p>
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                    <div class="border-bottom-black common-div imageContainer commonGutSpaceBtm">
                        <img v-bind:src="cosmosInfo.appData.footer.url" alt="">
                    </div>
                    <div class="row">
                        <div class="col-lg-3 col-xs-12 col-sm-12 col-md-4">
                            <div class="row">
                                <div v-for="range in cosmosInfo.appData.footer.range" class="col-lg-6 col-xs-6 col-sm-6 rangeContainer">
                                    <p><span :class="range.info"></span> {{range.info}}</p>
                                </div>
                            </div>
                        </div>
                        <div class="col-lg-9 commonGutSpaceTop">
                          <p>{{cosmosInfo.appData.footer.noteData}}</p>
                        </div>
                    </div>
                </div>
        </div>
    </div> 
</template>

<script>
    export default{
        props:{
            cosmosInfo: Object
        },
    }
</script>