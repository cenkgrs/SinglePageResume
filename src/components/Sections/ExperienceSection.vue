<script setup>
    import Timeline from 'primevue/timeline';
    import { ref } from "vue";
    import Card from 'primevue/card';

    const events = ref([
        { 
            status: 'Bilet.com - Intern', date: '2019 - 2020', icon: 'pi pi-ellipsis-v', color: '#673AB7',
            data: [
                {text: 'Worked as Intern and Junior Software Developer and participated in coding, testing and debugging at multiple projects. Worked on improving front-end side of Bilet.com and coded cancel-refund system for Airline tickets by integrating third-party API cancel system.'},
                {text: 'Designed and coded back-end of pocketwifiturkey.com, integrated virtual pos payment via Wirecard API also created a dashboard for this website'}
            ]
        }, { 
            status: 'Bilet.com - Software Engineer', date: '2020 - 2025', icon: 'pi pi-ellipsis-v', color: '#FF9800',
            data: [
                {text: 'Designed entertainment system by implementing multiple third-party APIs including offshore tickets, seated concert and theatre tickets'},
                {text: 'Coded entertainment turnstile system by creating RESTful API'},
                {text: 'Implemented multiple third-party APIs on subjects such as Ticket Insurance,'},
                {text: 'Integrated worldwide ferry ticket sale via usign DirectFerries API. Greek Island ferry tickets by implementing multiple Ferry Ticket APIs'},
                {text: 'Conducted thorough code refactoring and optimization, improving the efficiency and maintainability of legacy codebases while ensuring adherence to modern coding standards and practices.'},
                {text: 'Involved in redesign process of Bilet.com usign Vue.js and PrimeVue'}
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
                    <template #content>
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