<template>
    <div class="inline-block">
        <table class="inline-block counter">
            <tr @click="clickBall">
                <td>B</td>
                <td class="ball" v-for="(ballIndex) in ballCount" v-bind:key="ballIndex">●</td>
            </tr>
            <tr @click="clickStrike">
                <td >S</td>
                <td class="strike" v-for="(strikeIndex) in strikeCount" v-bind:key="strikeIndex">{{ strikeIndex }}</td>
            </tr>
            <tr>
                <td @click="clickOut">O</td>
                <td class="out" @click="clickOut" v-for="(outIndex) in outCount" v-bind:key="outIndex">{{ outIndex }}</td>
            </tr>
        </table>
    </div>
</template>

<script>
    export default {
        name: "Conter",
        data(){
            return {
                ballCount: [],
                strikeCount: [],
                outCount:[]
            }
        },
        methods:{
            clickBall(){
                if(this.ballCount.length < 3) {
                    this.ballCount.push('●');
                }else {
                    this.ballCount = [];
                }
            },
            clickStrike(){
                if(this.strikeCount.length < 2) {
                    this.strikeCount.push('●');
                }else {
                    this.strikeCount = [];
                }
            },
            clickOut(){
                if(this.outCount.length < 2) {
                    this.outCount.push('●');
                }else {
                    this.outCount = [];
                }
            }
        }
    }
</script>

<style scoped>
    .inline-block {
        display: inline-block;
    }
    .counter {
        font-size: 50px;
        background-color: black;
        color: aliceblue;
        width: 170px;
    }
    .ball {
        color: #00582b;
    }
    .strike {
        color: yellow;
    }
    .out {
        color: red;
    }
</style>