<script setup>

import Button from "primevue/button"

import { ref } from "vue";
import Dock from 'primevue/dock';

const activeTab = ref('home');

const changeTab = function (tab) {
    activeTab.value = tab;
}

const menuItems = ref([
    {
        label: 'Home',
        tab: 'home',
        icon: 'pi pi-home'
    },{
        label: 'Education',
        tab: 'education',
        icon: 'pi pi-info-circle'
        
    },{
        label: 'Skills',
        tab: 'skill',
        icon: 'pi pi-ellipsis-v'
    },{
        label: 'Projects',
        tab: 'project',
        icon: 'pi pi-github'
    },{
        label: 'Experience',
        tab: 'experience',
        icon: 'pi pi-list'
    },{
        label: 'Contact',
        tab: 'contact',
        icon: 'pi pi-user'
    },
]);

</script>

<template>
   
    <Dock :model="menuItems" position="bottom">
        <template #itemicon="{ item }">
            <Button 
                @click="changeTab(item.tab)" 
                :severity="activeTab == item.tab ? 'info' : 'secondary'" 
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