<script setup>
    import Tabs from 'primevue/tabs';
    import TabList from 'primevue/tablist';
    import Tab from 'primevue/tab';
    import TabPanels from 'primevue/tabpanels';
    import TabPanel from 'primevue/tabpanel';

    const items = [
        {
            'label': 'Artificial Intelligence Home Assistant',
            'route': 'art',
            'icon': 'pi pi-home',
        }, {
            'label': 'E-Commerce Site',
            'route': 'e-commerce',
            'icon': 'pi pi-shopping-cart',
        }, {
            'label': 'Laravel Chat Application',
            'route': 'chat',
            'icon': 'pi pi-whatsapp',
        }, {
            'label': 'Flutter Shipment Delivery App',
            'route': 'shipment',
            'icon': 'pi pi-clipboard',
        }
    ]

</script>

<template>
    <Tabs scrollable value="art">
        <TabList>
            <Tab v-for="tab in items" :key="tab.label" :value="tab.route">
                <i :class="tab.icon" class="mr-2 text-blue-500"/>
                <span>{{ tab.label }}</span>
            </Tab>
        </TabList>
        <TabPanels>
                <TabPanel value="art">
                </TabPanel>
                <TabPanel value="e-commerce">
                </TabPanel>
                <TabPanel value="chat">
                </TabPanel>
                <TabPanel value="shipment">
                </TabPanel>
            </TabPanels>
    </Tabs>
</template>