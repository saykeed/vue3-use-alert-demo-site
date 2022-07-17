
<template>
    <div class="demosite min-h-screen flex items-center justify-center">
        <div class="wrap w-[90%] max-w-[500px] mx-auto my-4">
          <h3 class="text-3xl text-center font-bold text-rose-700">Vue3-Use-Alert</h3>
            <p class="text-lg text-rose-600 font-medium">Message:</p>
            <textarea v-model="message" @click="destroyAlert"
            class="resize-none w-full h-22 border-2  outline-none border-rose-500 focus:shadow-md focus:shadow-rose-400 p-1 rounded-md"></textarea>

            <p class="text-lg text-rose-600 font-medium mt-2">Position:</p>
            <select v-model="position" class="w-full outline-none border-2 border-rose-600 rounded-md p-1 " @click="destroyAlert">
              <option value="topRight">topRight</option>
              <option value="topLeft">topLeft</option>
              <option value="bottomRight">bottomRight</option>
              <option value="bottomLeft">bottomLeft</option>
              <option value="topCenter">topCenter</option>
              <option value="bottomCenter">bottomCenter</option>
            </select>

            <!-- section for animation -->
            <p class="text-lg text-rose-600 font-medium mt-2">Animation:</p>
            <select v-model="animation" class="w-full outline-none border-2 border-rose-600 rounded-md p-1" @click="destroyAlert">
              <option value="slideX">slideHorizontaly</option>
              <option value="slideY">slideVertically</option>
            </select>

          <!-- section for background color -->
            <p class="text-lg text-rose-600 font-medium mt-2">Background Color: <i class="text-sky-400 text-sm">click to select color</i></p>
            <input type="color" v-model="bgColor" class="w-[100px] h-[50px]" @click="destroyAlert">

            <!-- section for text color -->
            <p class="text-lg text-rose-600 font-medium mt-2">Text Color: <i class="text-sky-400 text-sm">click to select color</i></p>
            <input type="color" v-model="textColor" class="w-[100px] h-[50px]" @click="destroyAlert">

            <!-- section for auto close input -->
            <p class="text-lg text-rose-600 font-medium mt-2">Auto Close: <i class="text-sky-400 text-sm">Input the amount of milliseconds or leave it null to disable autoclose</i></p>
            <input type="number" v-model="autoClose" class="w-full outline-none border-2 border-rose-600 rounded-md p-1" @click="destroyAlert">

            <!-- button to activate alert box -->
            <button @click="controlAlert" class="mt-3 mx-auto block bg-rose-600 text-white p-2 rounded shadow-lg hover:bg-rose-800">Activate Alert</button>

            <p class="text-sm text-rose-700 text-center font-bold">
              If you'll like to contribute to it, click on the link fixed to the left of this site. Gracias!!!
            </p>

            <a href="https://github.com/saykeed/vue3-use-alert.git" target="_blank"
              class="fixed top-1/2 -translate-y-1/2 left-0 py-3 px-2 bg-rose-500 hover:bg-rose-600 text-white text-xl"
            >
              <i class="fa fa-github"></i>
            </a>
        </div>
    </div>
    <vue3-alert-box/>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue';
import { useAlert } from 'vue3-use-alert'

const { openAlert, closeAlert } = useAlert()

    // variables
    const message = ref('Hy developer, you wanna edit me, pls go ahead!!!')
    const position = ref('topRight')
    const animation =  ref('slideX')
    const bgColor = ref('#d21e1e')
    const textColor = ref('#ffffff')
    const autoClose = ref()

    const controlAlert = () => {
      openAlert({
        message: message.value,
        position: position.value,
        animation: animation.value,
        backgroundColor: bgColor.value,
        textColor: textColor.value,
        autoClose: autoClose.value
      })
    }

    const destroyAlert = () => {
      closeAlert()
    }

    onMounted(() => {
      openAlert({
        message: "You are Welcome to vue3-use-alert-demo",
        position: 'topRight',
        animation: 'slideX',
        backgroundColor: 'purple',
        textColor: 'white',
        autoClose: null
      })
    })
</script>

<style>
  
</style>
