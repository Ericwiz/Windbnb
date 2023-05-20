<template>
    <div class="d-flex d-sm-none justify-space-between max-width mx-auto ml-16 pt-4">
        <span>Enter your search</span>
        <v-icon @click="$emit('close')" icon="mdi-close-thick" class="pt-4 pr-8"></v-icon>
    </div>
    <div class="d-flex flex-column flex-sm-row justify-center mt-10 ml-16 w-75">
        <v-select
            placeholder="Hensiki, FinLand"
            density="compact"
            variant="outlined"
            prepend-inner-icon="mdi-map-marker"
            :items="getLocationOptions"
            class=""
            >
        </v-select>


        <v-combobox
            density="compact"
            class=""
             variant="outlined"
             label="Add guests"
             :items="['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']">
        </v-combobox>
        <v-btn class="rounded-lg align-self-start text-caption bg-red px-4 d-flex flex-row justify-space-between align-center" size="x-large" flat density="compact">
            <v-icon icon="mdi-magnify" class=""></v-icon>
            <span>Search</span>
        </v-btn>
    </div>
</template>

<script>
import locationData from '../assets/stays.json'
export default {
    emits:['close'],
    data() {
            return {
                locations: locationData,
            }
        },
    computed: {
        getLocationOptions() {
            return this.locations.map(location => {
            return location.city + ', ' + location.country
            });
        }
    }
}
</script>

<style scoped>
.height {
    height: 55px;
}

.outline {
    outline: none;
}

.max-width {
    max-width: 90%;
}
</style>