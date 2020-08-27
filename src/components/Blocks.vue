<template>
    <div id="block-container">
        <ul>
            <li v-for="(val,index) in numbers" :key="index" :class="['block-'+val,'plain']">
                <div :class="['block-'+val]"></div>
                <span>{{ val }}</span>
            </li>
        </ul>
    </div>
</template>

<script>
import { eventBus } from '../main';
export default {
    name: 'Blocks',
    props: {
        sizeOfBlocks: Number
    },
    data(){
        return{
            numbers: [],
            temp: ''
        }
    },
    methods: {
        shuffleBlocks(){
            this.numbers.sort(() => Math.random() - 0.5);
        },
        sortBlocks(){
            this.numbers.sort();
        }
    },
    created(){
        for(let i=1;i<=this.sizeOfBlocks;i++)
            this.numbers.push(i)
        eventBus.$on('shuffleBlocks',this.shuffleBlocks); 
        eventBus.$on('sortBlocks',this.sortBlocks);
    }
}
</script>

<style scoped>
#block-container{
    display: inline-block;
    width: 75%;
    height: 90%
}
ul{
    /* display: table; */
    list-style-type:none;
    padding: 0px;
    height: 100%;
}
li{
    display: inline-block;
    width: calc(30% - 1px);
    height: 30%;
    /* vertical-align: middle; */
    text-align: center;
    color: white;
    font-size:5rem
}
span{
    /* display: inline-block; */
    
    line-height: 130px;
}

.block-1{
    background-color: #6F98A8;
}
.block-2{
    background-color: #2B8EAD;
}
.block-3{
    background-color: #2F454E;
}
.block-4{
    background-color: #2B8EAD;
}
.block-5{
    background-color: #2F454E;
}
.block-6{
    background-color: #EFEFEF;
}
.block-7{
    background-color: #EFEFEF;
}
.block-8{
    background-color: #72C3DC;
}
.block-9{
    background-color: #2F454E;
}

@media (max-width: 375px) {
    #block-container{
        width: 100%;
        height: 80%
    }
    ul{
        height: 100%;
    }
    li{
        width: 90%;
        height: 10%;
        font-size: large;
        font-weight: bold;
        margin: 2px 10px;
        color: black;
    }
    li.plain{
        background-color: lightgray;
    }
    li div {
        display: inline-block;
        content: '';
        width: 3%;
        height: 100%;
        float: left;
    }
    span{
        /* display: inline-block; */
        
        line-height: 45px;
    }
}
</style>