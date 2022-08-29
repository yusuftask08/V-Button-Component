<template>
  <div class="app-view">
    <div id="app">
      <img alt="Vue logo" src="./assets/logo.png">
    </div>
    <div class="buttons">
      <Button
       v-for="button in buttonSm" :key="button.id" 
       :size="button.size" 
       :color="button.color" 
       :innerText="button.innerText" 
       @onClick="button.onClick()">

       {{button.vSlot}}
      </Button>
    </div>
    <div class="buttons">
      <Button
       v-for="button in buttonMd" :key="button.id" 
       :size="button.size" 
       :color="button.color" 
       :innerText="button.innerText" 
       @onClick="button.onClick()">

       {{button.vSlot}}
      </Button>
    </div>
    <div class="buttons">
      <Button
       v-for="button in buttonLg" :key="button.id" 
       :size="button.size" 
       :color="button.color" 
       :innerText="button.innerText" 
       @onClick="button.onClick()">

       {{button.vSlot}}
      </Button>
    </div>
    <div class="buttons">
      <Button
       v-for="button in buttonxLg" :key="button.id" 
       :size="button.size" 
       :color="button.color" 
       :innerText="button.innerText" 
       @onClick="button.onClick()">

       {{button.vSlot}}
      </Button>
    </div>
  </div>
</template>

<script>
import Button from '@/components/Button/index.vue'
import buttons from '../public/buttons.json'

export default {
  name: 'App',
  components: {
    Button
  },
  methods: {
    btnClick() {
      alert('butona tıklandı')
    }
  },
  computed:{
    buttonSm(){
      return buttons.map((object) => {
        return {
          ...object,
          onClick(){
            alert('Small butona tıklandı')
          }
        }
      })
    },
    buttonMd(){
      return buttons.map((object) => {
        return {
          ...object,
          size:'medium',
          onClick(){
            alert('Medium butona tıklandı')
          }
        }
      })
    },
    buttonLg(){
      return buttons.map((object) => {
        return {
          ...object,
          size:'large',
          onClick(){
            alert('Large butona tıklandı')
          }
        }
      })
    },
    buttonxLg(){
      return buttons.map((object) => {
        return {
          ...object,
          size:'xLarge',
          onClick(){
            alert('xLarge butona tıklandı')
          }
        }
      })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.buttons {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
