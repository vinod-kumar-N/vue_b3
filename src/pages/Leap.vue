<template>
    <div class="leap page-section" id="leap">
        <div class="container-fluid common-page-head">
            <div class="container">
                <div>
                    <h3>{{info.chapter}}</h3>
                </div>
                <div>
                    <h1>{{info.title}}</h1>
                </div>
            </div> 
        </div>
        <div class="container-fluid common-page-subhead">
            <div class="container">
                <div>
                    <h2>{{info.head}}</h2>
                </div>
            </div> 
        </div>
        <div class="container-fluid">
                <div v-if="signed == 'true'">
                <div class="container common-div">
                    <div class="row common-mob-padd-fix cat-keep-container">
                        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
                            <p>{{info.bodyText.basicInfo}}</p>
                            <h3>{{info.bodyText.headerInfo}}</h3>
                            <p>{{info.bodyText.workInfo}}</p>
                            <p class="blue">{{info.bodyText.petCompare}}</p>
                            <p>{{info.bodyText.cageFit}}</p>
                            <p class="blue">{{info.bodyText.cageSchema}}</p>
                            <p>{{info.bodyText.ownerInfo}}</p>
                            <p class="blue">{{info.bodyText.petRoom}}</p>
                        </div>
                        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 imageContainer h-100" :style=style>
                            <img v-bind:src="info.urlDual" />
                        </div>
                    </div>
                    <div class="row common-card toggleVolume">
                        <div class="col-lg-6 col-md-12 col-sm-12 col-xs-12">
                            <h2 class="commonGutSpaceBtm">{{info.toggleVolume.headerInfo}}</h2>
                            <div class="common-card-info card" v-bind:class="{ active: toggle }">
                                <div v-show="toggle">
                                <h3 class="blue">{{info.toggleVolume.toggleInfoSecondary.headerInfo}}</h3>
                                    <p>{{info.toggleVolume.toggleInfoSecondary.bodyText}}</p>
                                </div>
                                <div v-show="!toggle" >
                                    <h3 class="blue">{{info.toggleVolume.toggleInfoPrimary.headerInfo}}</h3>
                                    <p>{{info.toggleVolume.toggleInfoPrimary.bodyText}}</p>
                                    <p>{{info.toggleVolume.toggleInfoPrimary.extraInfo}}</p>
                                </div>
                            <button class="btn btn-primary btn-lg" v-on:click="toggle = !toggle"><span v-show="toggle">{{info.toggleVolume.toggleInfoSecondary.btnText}}</span><span v-show="!toggle">{{info.toggleVolume.toggleInfoPrimary.btnText}}</span></button>
                            </div>
                        </div>
                        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 imageContainer d-none d-md-none d-lg-block" >
                             <img v-bind:src="info.toggleVolume.url" />
                        </div>
                    </div>
                    <div class="row common-card toggleVelocity common-mob-padd-fix">
                        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 imageContainer d-none d-md-none d-lg-block" >
                             <img v-bind:src="info.toggleVelocity.url" />
                        </div>
                        <div class="col-lg-6 col-md-12 col-sm-12 col-xs-12">
                            <div class="common-card-info card" v-bind:class="{ active: velocity }">
                                <div v-show="velocity">
                                <h3 class="blue">{{info.toggleVelocity.toggleInfoSecondary.headerInfo}}</h3>
                                    <p>{{info.toggleVelocity.toggleInfoSecondary.bodyText}}</p>
                                </div>
                                <div v-show="!velocity" >
                                    <h3 class="blue">{{info.toggleVelocity.toggleInfoPrimary.headerInfo}}</h3>
                                    <p>{{info.toggleVelocity.toggleInfoPrimary.bodyText}}</p>
                                    <p>{{info.toggleVelocity.toggleInfoPrimary.extraInfo}}</p>
                                </div>
                            <button class="btn btn-primary btn-lg" v-on:click="velocity = !velocity"><span v-show="velocity">{{info.toggleVelocity.toggleInfoSecondary.btnText}}</span><span v-show="!velocity">{{info.toggleVelocity.toggleInfoPrimary.btnText}}</span></button>
                            </div>
                        </div>
                    </div>
                    <div class="row common-card toggleVariety common-mob-padd-fix">
                        <div class="col-lg-6 col-md-12 col-sm-12 col-xs-12">
                            <div class="common-card-info card" v-bind:class="{ active: variety }">
                                <div v-show="variety">
                                <h3 class="blue">{{info.toggleVariety.toggleInfoSecondary.headerInfo}}</h3>
                                    <p>{{info.toggleVariety.toggleInfoSecondary.bodyText}}</p>
                                </div>
                                <div v-show="!variety" >
                                    <h3 class="blue">{{info.toggleVariety.toggleInfoPrimary.headerInfo}}</h3>
                                    <p>{{info.toggleVariety.toggleInfoPrimary.bodyText}}</p>
                                    <p>{{info.toggleVariety.toggleInfoPrimary.extraInfo}}</p>
                                </div>
                            <button class="btn btn-primary btn-lg" v-on:click="variety = !variety"><span v-show="variety">{{info.toggleVariety.toggleInfoSecondary.btnText}}</span><span v-show="!variety">{{info.toggleVariety.toggleInfoPrimary.btnText}}</span></button>
                            </div>
                        </div>
                        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 imageContainer d-none d-md-none d-lg-block" >
                             <img v-bind:src="info.toggleVariety.url" />
                        </div>
                </div>
                <div class="row common-card toggleDynamic common-mob-padd-fix">
                        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 imageContainer d-none d-md-none d-lg-block" >
                             <img v-bind:src="info.toggleDynamic.url" />
                        </div>
                        <div class="col-lg-6 col-md-12 col-sm-12 col-xs-12">
                            <div class="common-card-info card" v-bind:class="{ active: dynamic }">
                                <div v-show="dynamic">
                                <h3 class="blue">{{info.toggleDynamic.toggleInfoSecondary.headerInfo}}</h3>
                                    <p>{{info.toggleDynamic.toggleInfoSecondary.bodyText}}</p>
                                </div>
                                <div v-show="!dynamic" >
                                    <h3 class="blue">{{info.toggleDynamic.toggleInfoPrimary.headerInfo}}</h3>
                                    <p>{{info.toggleDynamic.toggleInfoPrimary.bodyText}}</p>
                                    <p>{{info.toggleDynamic.toggleInfoPrimary.extraInfo}}</p>
                                </div>
                            <button class="btn btn-primary btn-lg" v-on:click="dynamic = !dynamic"><span v-show="dynamic">{{info.toggleDynamic.toggleInfoSecondary.btnText}}</span><span v-show="!dynamic">{{info.toggleDynamic.toggleInfoPrimary.btnText}}</span></button>
                            </div>
                        </div>
                </div>
                <div class="row common-card toggleGlobal common-mob-padd-fix">
                        <div class="col-lg-6 col-md-12 col-sm-12 col-xs-12">
                            <div class="common-card-info card" v-bind:class="{ active: global }">
                                <div v-show="global">
                                <h3 class="blue">{{info.toggleGlobal.toggleInfoSecondary.headerInfo}}</h3>
                                    <p>{{info.toggleGlobal.toggleInfoSecondary.bodyText}}</p>
                                </div>
                                <div v-show="!global" >
                                    <h3 class="blue">{{info.toggleGlobal.toggleInfoPrimary.headerInfo}}</h3>
                                    <p>{{info.toggleGlobal.toggleInfoPrimary.bodyText}}</p>
                                    <p>{{info.toggleGlobal.toggleInfoPrimary.extraInfo}}</p>
                                </div>
                            <button class="btn btn-primary btn-lg" v-on:click="global = !global"><span v-show="global">{{info.toggleGlobal.toggleInfoSecondary.btnText}}</span><span v-show="!global">{{info.toggleGlobal.toggleInfoPrimary.btnText}}</span></button>
                            </div>
                        </div>
                        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 imageContainer d-none d-md-none d-lg-block" >
                             <img v-bind:src="info.toggleGlobal.url" />
                        </div>
                </div>
            </div>
        </div>
        <div class="container common-div" v-else>
            <div class="row flexthis">
                <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12"><p>{{info.textPrimary}}</p></div>
                <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12"><p>{{info.textSecondary}}</p></div>
            </div>
        </div>
    </div> 
    <div class="common-page-head leapFooter common-border-bottom" v-if="signed == 'true'">
                    <div class="container common-abs-container">
                    <div class="row">
                            <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
                                <p>{{info.footerContent.content}}</p>
                            </div>
                            <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 imageContainer absContainer" >
                                <img v-bind:src="info.footerContent.url" />
                            </div>
                    </div>
                    </div>
    </div>
</div>
</template>

<script>
    export default{
        props:{
            info: Object,
            signed: String,
        },
        data(){
        return {
            toggle: this.toggle,
            velocity: this.velocity,
            variety: this.variety,
            dynamic: this.dynamic,
            global: this.global
            }
        },
        computed: {
            style () {
            return 'backgroundImage: url( "' + this.info.url + '")';
            }
        },
    }
</script>