<template>
  <div id="app">
    <Blocks :sizeOfBlocks="sizeOfBlocks"/>
    <Controls />
  </div>
</template>

<script>
import Blocks from './components/Blocks'
import Controls from './components/Controls'

export default {
  name: 'App',
  components: {
    Blocks,
    Controls
  },
  data(){
    return{
      sizeOfBlocks: 9
    }
  }
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 500px;
  display: flex;
  flex-direction: row;
}

@media (max-width: 375px) {

  #app {
  width: 100%;
  height: 600px;
  display: flex;
  flex-direction: column-reverse;
}

}
</style>
