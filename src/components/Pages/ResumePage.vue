<script setup>
    import { ref } from 'vue';
    import DockMenu from '../DockMenu.vue';

    import HomeSection from '../Sections/HomeSection.vue';
    import ProjectsSection from '../Sections/ProjectsSection.vue';
    import SkillsSection from '../Sections/SkillsSection.vue';
    import ExperienceSection from '../Sections/ExperienceSection.vue';
    import EducationSection from '../Sections/EducationSection.vue';
    import ContactSection from '../Sections/ContactSection.vue';

    const activeTab = ref('home');

    const changeTab = function (tab) {
        activeTab.value = tab;
    }

</script>

<template>

    <HomeSection v-show="activeTab == 'home'"/>
    <ProjectsSection v-show="activeTab == 'projects'"/>
    <SkillsSection v-show="activeTab == 'skills'"/>
    <ExperienceSection v-show="activeTab == 'experience'"/>
    <EducationSection v-show="activeTab == 'education'"/>
    <ContactSection v-show="activeTab == 'contact'"/>

    <DockMenu @changeTab="changeTab" :activeTab="activeTab"/>

</template>