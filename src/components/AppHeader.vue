<template>
        <!-- <div v-show="showHeader" class="bg-red h-100 w-100 position-child">
            <HeaderBaseVue />
        </div> -->

        <v-overlay
          v-model="showHeader"
          contained
          class="d-flex m-auto"
        > 
            <v-card class="bg-white width-2 m-auto" >
                <HeaderBaseVue v-on:close="showHeader = false" />
            </v-card>
        </v-overlay>
        <div class="d-flex flex-column flex-sm-row justify-space-between max-width mx-auto">
            <div class=" d-flex flex-space-between">
                <div class="pt-4 pr-2">
                    <img src="../assets/logo.png" alt="" />
                </div>
                <v-switch @click="toggleTheme"></v-switch>
            </div>

            <div class="d-flex flex-row justify-end align-self-center">
            <v-btn @click="showHeader = !showHeader" color="white" class="rounded-lg text-caption text-grey-darken-1 w-100">
                    <span class="text-capitalize">finland</span>
                    <v-divider class="mx-2" vertical ></v-divider>
                    Add guests
                    <v-divider class="mx-2" vertical ></v-divider>
                    <v-icon icon="mdi-magnify" class="text-red"></v-icon>
                </v-btn>
            </div>
        </div>
</template>

<script>
import { useTheme } from 'vuetify'
import HeaderBaseVue from '../components/HeaderBase.vue'
    export default {
        components: {HeaderBaseVue},
        data() {
            return {
                showHeader: false
            }
        },

  setup () {
    const theme = useTheme()

    return {
      theme,
      toggleTheme: () => theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
    }
  },
}
</script>

<style scoped>
.max-width {
    max-width: 90%;
}
.position-child{
    position: absolute;
    top: 0;
    z-index: 100;
}
.width-2{
    width:  100vw;
    height: 50vh;
}
</style>