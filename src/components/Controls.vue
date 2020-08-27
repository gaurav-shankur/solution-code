<template>
    <div id="controls-container">
        <button class="shuffle-btn" @click="shuffle">SHUFFLE</button>
        <button class="sort-btn" @click="sort">SORT</button>
    </div>
</template>

<script>
import { eventBus } from '../main';
export default {
    name: 'Controls',
    data(){
        return{
            
        }
    },
    methods: {
        shuffle(){
            eventBus.$emit('shuffleBlocks');
        },
        sort(){
            eventBus.$emit('sortBlocks');
        }
    }
}
</script>

<style scoped>
#controls-container{
    display: inline-block;
    width: 25%
}

button{
    border: 0px solid transparent;
    background-color: #72C3DC;
    box-shadow: 1px 3px #2B8EAD;
    border-radius: 4px;
    width: 70%;
    height: 20px;
    margin: 10px 15%;
    color: white;
    font-weight: bold;
}
button:focus{
        outline: none;
}

@media (max-width: 375px) {
    
    #controls-container{
        display: inline-block;
        width: 100%;
    }
    button{
        display: inline-block;
        margin: 0px;
        width:25%;
        height: 50px;
    }
    .shuffle-btn{
        margin-right: 5px;
    }
    .shuffle-btn{
        margin-left: 5px;
    }
}
</style>