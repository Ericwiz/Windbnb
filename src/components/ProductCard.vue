<template>
    <div class="d-flex flex-row justify-space-between mb-6 mr-4 ml-4">
        <h4>Stays in FinLand</h4>
        <span class="text-caption">12+ stays</span>
    </div>
    <v-row class="mx-auto">
        <v-col v-for="data in datas" :key="data" cols="12" sm="6" md="4">
            <v-card
            class="rounded-lg">
                <v-img
                :src="data.photo"
                height="200px"
                cover
            ></v-img>

            <div class="d-flex justify-space-between">
                <div class="d-flex flex-row justify-space-between px-2 py-4">
                    <p v-if="data.superHost" class="text-uppercase text-caption border rounded-xl px-2">Superhost</p>
                    <span class="text-capitalize text-grey-darken-1 text-truncate text-caption px-2">{{ data.type }}</span>
                    <span class="text-grey-darken-1 text-caption" v-if="data.beds < 3 && data.beds != null">{{ data.beds }} beds</span>

                </div>
                <div class="px-2 py-4">
                    <v-icon icon="mdi-star" class="text-body text-amber-darken-4"></v-icon>
                    <span class="px-2">{{ data.rating }}</span>
                </div>
            </div>

            <h5 class="px-2 py-2">{{ data.title }}</h5>
            </v-card>
        </v-col>
    </v-row>
</template>

<script>
    export default {
        props: {
            datas: Array
        }
    }
</script>

<style scoped>
</style>