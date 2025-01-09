<script setup>

import Button from "primevue/button"

import { ref, defineProps } from "vue";
import Dock from 'primevue/dock';


const menuItems = ref([
    {
        label: 'Home',
        tab: 'home',
        icon: 'pi pi-home'
    },{
        label: 'Projects',
        tab: 'projects',
        icon: 'pi pi-github'
    },{
        label: 'Skills',
        tab: 'skills',
        icon: 'pi pi-ellipsis-v'
    },{
        label: 'Experience',
        tab: 'experience',
        icon: 'pi pi-list'
    },{
        label: 'Education',
        tab: 'education',
        icon: 'pi pi-info-circle'
        
    },{
        label: 'Contact',
        tab: 'contact',
        icon: 'pi pi-user'
    },
]);

const props = defineProps(['activeTab']);

</script>

<template>
    <Dock :model="menuItems" position="bottom">
        <template #itemicon="{ item }">
            <Button 
                @click="$emit('changeTab', item.tab)" 
                :severity="props.activeTab == item.tab ? 'info' : 'secondary'" 
                variant="text" :label="item.label" :icon="item.icon"
                type="button" class="text-lg"/>
        </template>
    </Dock>
</template>

<style>
    .p-dock-item{
        margin-right: 1rem;
        margin-left: 2rem;
        text-align: center;
        width: 5rem;
    }
</style>