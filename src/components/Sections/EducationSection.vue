<script setup>
    import Timeline from 'primevue/timeline';
    import { ref } from "vue";
    import Card from 'primevue/card';

    const events = ref([
        { 
            status: 'Sabancı 50.Yıl Anadolu Lisesi', date: '2012 - 2016', icon: 'pi pi-ellipsis-v', color: '#9C27B0',
            data: null
        }, { 
            status: 'Istanbul University - Computer Engineering', date: '2016 - 2020', icon: 'pi pi-ellipsis-v', color: '#673AB7',
            data: [
                {text: 'Created physical body and web interface of Artifical Intelligence Home Assistant as Graduation Project (details on personal projects)'},
                {text: 'Developed Android News Application for Mobile Programming Course (details on personal projects)'},
                {text: 'Developed hospital management system with JavaFaces'},
            ]
        }
    ]);

</script>

<template>

    <div class="card">
        <Timeline :value="events" class="w-full">
            <template #marker="slotProps">
                <span class="flex w-8 h-8 items-center justify-center text-white rounded-full z-10 shadow-sm" :style="{ backgroundColor: slotProps.item.color }">
                    <i :class="slotProps.item.icon"></i>
                </span>
            </template>
         
            <template #content="slotProps">
                <Card class="mt-4">
                    <template #title>
                        {{ slotProps.item.status }}
                    </template>
                    <template #subtitle>
                        <span class="font-medium text-sm">{{ slotProps.item.date }}</span>
                    </template>
                    <template v-if="slotProps.item.data" #content>
                        <div class="flex mt-2" v-for="data in slotProps.item.data" v-bind:key="data" style="align-items: center;">
                            <i class="text-blue-400 pi pi-minus mr-2 text-sm"></i>
                            <p class="font-medium text-sm">
                                {{ data.text }}
                            </p>
                        </div>
                        <Button label="Read more" text></Button>
                    </template>
                </Card>

            </template>
        </Timeline>
    </div>

</template>