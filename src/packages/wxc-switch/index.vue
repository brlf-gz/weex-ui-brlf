<template>
    <div class="switch" :style="switchStyle" @click="change">
        <div ref="circle" class="circle" :style="circleStyle"></div>
    </div>
</template>

<script>
    const animation = weex.requireModule('animation');

    export default {
        name: "wxc-switch",
        props: {
            width:{default:'100px'},
            height:{default:'50px'},
            checked:{default:false},
            disabled:{default:false},
        },
        data () {
            return {
                isChecked: false,
            }
        },

        mounted(){
            this.isChecked = this.checked;

            const widthValue = parseInt(this.width.substring(0, this.width.length - 2));
            const heightValue = parseInt(this.height.substring(0, this.height.length - 2));

            animation.transition(this.$refs.circle, {
                styles: {
                    transform: `translateX(${this.isChecked ? widthValue - heightValue : 0}px)`,
                    transformOrigin: 'center center'
                },
                duration: 0, //ms
                timingFunction: 'ease',
                delay: 0 //ms
            })
        },

        computed:{
            switchStyle(){
                let opacity = this.disabled ? 0.3 : 1;
                return {
                    width:this.width,
                    height: this.height,
                    backgroundColor: this.isChecked ? `rgba(117, 209, 113, ${opacity})` : `rgba(255, 255, 255,  ${opacity})`,
                }
            },
            circleStyle(){
                return {
                    width: this.height,
                    height: this.height,
                }
            }
        },

        methods: {
            change(){
                if (this.disabled){
                    return;
                }
                this.isChecked = !this.isChecked;
                this.$emit('change',{
                    value:this.isChecked
                });
                const widthValue = parseInt(this.width.substring(0, this.width.length - 2));
                const heightValue = parseInt(this.height.substring(0, this.height.length - 2));

                animation.transition(this.$refs.circle, {
                    styles: {
                        transform: `translateX(${this.isChecked ? widthValue - heightValue : 0}px)`,
                        transformOrigin: 'center center'
                    },
                    duration: 600, //ms
                    timingFunction: 'ease',
                    delay: 0 //ms
                })
            }
        },
    }

</script>

<style scoped>
    .switch{
        border-width: 1px;
        border-color: #dcdcdc;
        border-radius: 45px;
    }
    .circle{
        border-width: 1px;
        border-color: #dcdcdc;
        border-radius: 45px;
        background-color: white;
    }
</style>