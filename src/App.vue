
<template>
    <div class="app text-red-600 text-center p-4  min-h-screen w-full bg-sky-200">
      <div class="intro max-w-[500px] mx-auto">
          <h1 class="text-2xl">Hy guys, I hope you are good. Nothing much to see here, just a demo of how the vue3-use-alert plugin works</h1>
          <p class="xl mt-5">Play with the inputs below to see how it works</p>
      </div>

        <div class="playGround p-2 max-w-[600px] mx-auto border-2 border-red-600 rounded-lg">
          <form @submit.prevent="controlAlert">
            <label for="message">message: </label>
            <textarea class="w-full max-w-[300px] h-24 resize-none p-2" id="message" v-model="message"></textarea>
            <div class="inputs">
              <div class="position my-2">
                  <label for="position">Position: </label>
                  <select id="position p-2" v-model="position">
                    <option value="topLeft">topLeft</option>
                    <option value="topRight">topRight</option>
                    <option value="bottomLeft">bottomLeft</option>
                    <option value="bottomRight">bottomRight</option>
                    <option value="topCenter">topCenter</option>
                    <option value="bottomCenter">bottomCenter</option>
                  </select>
              </div>
              
              <div class="animation my-2">
                  <label for="animation">Animation: </label>
                  <select id="animation p-2" v-model="animation">
                    <option value="slideX">slideX</option>
                    <option value="slideY">slideY</option>
                  </select>
              </div>

              <div class="bgColor my-2">
                <label for="bgColor">Background Color</label>
                <input class="p-2" type="text" id="bgColor" placeholder="hex values, rgb etc" v-model="bgColor">
              </div>

              <div class="textColor my-2">
                <label for="textColor">Text Color</label>
                <input class="p-2" type="text" id="textColor" placeholder="hex values, rgb etc" v-model="textColor">
              </div>

              <div class="autoClose my-2">
                <label for="autoClose">Auto Close</label>
                <input class="p-2" type="number" id="autoClose" v-model="autoClose">
              </div>
            </div>
            <button type="submit" class="bg-red-500 text-white text-center px-3 py-2 rounded">Load Alert</button>
          </form>
        </div>
    </div>
    <!-- <vue3-alert-box/> -->
</template>

<script setup lang="ts">
import { ref } from 'vue';
// import { useAlert } from 'vue3-use-alert'

// const { openAlert } = useAlert()

    // variables
    const message = ref('Hy there, you wanna edit me, pls go ahead, Cheers!!!!!')
    const position = ref('topRight')
    const animation =  ref('slideX')
    const bgColor = ref('purple')
    const textColor = ref('white')
    const autoClose = ref(4000)

    const controlAlert = () => {
      console.log('worining')
      // openAlert({
      //   message: message.value,
      //   position: position.value,
      //   animation: animation.value,
      //   backgroundColor: bgColor.value,
      //   textColor: textColor.value,
      //   autoClose: autoClose.value
      // })
    }
</script>

<style>
  
</style>
