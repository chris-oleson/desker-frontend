<template>
    <v-navigation-drawer permanent floating elevation="4">
        <v-list class="font-weight-light pa-0">
            <v-list-item v-for="view in store.views" v-bind:key="view" replace slim class="py-4" @click="changeView(view.position)">{{ view.name }}</v-list-item>
        </v-list>
    </v-navigation-drawer>
</template>

<script setup>
import { useStore } from '/src/pinia'
const store = useStore()
import { useRouter } from 'vue-router'
const router = useRouter()

function changeView(view) {
    router.push('/view/' + view)
}
</script>