<script setup>
    import Timeline from 'primevue/timeline';
    import { ref } from "vue";

    const events = ref([
        { status: 'Sabancı 50.Yıl Anadolu Lisesi', date: '2012 - 2016', icon: 'pi pi-graduation-cap', color: '#9C27B0'},
        { status: 'Istanbul University - Computer Engineering', date: '2016 - 2020', icon: 'pi pi-graduation-cap', color: '#9C27B0'},
        { status: 'Bilet.com - Intern', date: '2019 - 2020', icon: 'pi pi-ellipsis-v', color: '#673AB7' },
        { status: 'Bilet.com - Software Engineer', date: '2020 - 2025', icon: 'pi pi-ellipsis-v', color: '#FF9800' },
    ]);

</script>

<template>

    <div class="card">
        <Timeline :value="events" align="alternate" class="w-full">
            <template #marker="slotProps">
                <span class="flex w-8 h-8 items-center justify-center text-white rounded-full z-10 shadow-sm" :style="{ backgroundColor: slotProps.item.color }">
                    <i :class="slotProps.item.icon"></i>
                </span>
            </template>
            <template #opposite="slotProps">
                <small class="text-surface-500 dark:text-surface-400">{{slotProps.item.date}}</small>
            </template>
            <template #content="slotProps">
                <span class="font-medium">{{ slotProps.item.status }}</span>
            </template>
        </Timeline>
    </div>

</template>

<style>
    .p-timeline-event-connector {
        background-color: gray;
    }
</style>