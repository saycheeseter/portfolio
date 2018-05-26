<template>
        <div class="box--whole">
            <div class="portfolio--image">
                sample
            </div>
            <div class="portfolio--content">
                <div class="portfolio--about" id="scrollbar--dark">
                    <p v-show="briefAbout" class="about--text">
                        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Vel illum unde iure sint veniam eum nostrum consequuntur error, totam odit impedit, temporibus officiis quisquam, natus beatae atque dolorum. Voluptas, fuga?
                    </p>
                    <p v-show="infoFlag || awardFlag" @click="closeAbout" class="close-button">x</p>
                    <transition-group name="slide-fade" mode="in-out" class="transition--row">
                        <basic-info v-show="infoFlag" key="info"></basic-info>
                        <awards v-show="awardFlag" key="award"></awards>
                    </transition-group>

                </div>
                <div class="portfolio--nav">
                    <ul>
                        <li @click="infoShow()">
                            Basic Info
                        </li>
                        <li @click="awardShow()">
                            Achievements & Awards
                        </li>
                    </ul>
                </div>
            </div>
        </div>
</template>
<script>
import BasicInfo from './AboutSelf'
import Awards from './AboutAcheivements'
export default {
    data() {
        return {
            infoFlag: false,
            awardFlag: false,
            briefAbout:true
        }
    },
    components: {
        'basic-info' : BasicInfo,
        'awards' : Awards
    },
    methods: {
        infoShow() {
            this.briefAbout = false
            this.infoFlag = true
            if(this.awardFlag)
                this.awardFlag = false
            
        },
        awardShow() {
            this.briefAbout = false
            this.awardFlag = true
            if(this.infoFlag)
                this.infoFlag = false
        },
        closeAbout() {
            this.awardFlag = false
            this.infoFlag = false
            this.briefAbout = true
        }
    }
}
</script>


<style lang="scss" scoped>
    .slide-fade-enter-active {
        transition: all .3s ease;
    }
    .slide-fade-leave-active {
        transition: all .1s cubic-bezier(1.0, 0.5, 0.8, 1.0);
    }
    .slide-fade-enter, .slide-fade-leave-to
    /* .slide-fade-leave-active below version 2.1.8 */ {
        transform: translateX(10px);
        opacity: 0;
    }
    h1{ 
        color:red;
    }
    .box--whole{
        width: 65%;
        height: 65%;
        background: rgb(255, 255, 255);
        display: flex;
        justify-content: space-between;
        .portfolio--image{
            width: 50%;
            background: #000;
        }
        .portfolio--content{
            width: 50%;
            display: flex;
            flex-direction: column;

            .portfolio--about{
                height: 100%;
                padding: 10px;
                flex: 1;
                overflow-y: auto;
                .about--text{
                    margin-left: 10px;
                    font-family: 'Montserrat', sans-serif;
                    font-size: 20px;
                }
                .transition--row{
                    display: flex;
                    flex-direction: row;
                }
                .close-button{
                    margin: 0;
                    padding: 0;
                    text-align: right;
                }
            }
            .portfolio--nav{
                ul{
                    display: flex;
                    align-items: center;
                    justify-content: space-around;
                    list-style:none;
                    li{
                        font-family: 'Kanit', sans-serif;
                    }
                }
            }
        }
    }
</style>
