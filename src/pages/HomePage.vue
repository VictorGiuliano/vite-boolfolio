<script>
import axios from 'axios';
import AppCard from '../components/AppCard.vue';
const apiBaseUrl = 'http://127.0.0.1:8000/api/';
export default {
    name: 'Homepage',
    components: { AppCard },
    data: () => ({
        projects: []
    }),
    methods: {
        fetchProjects() {
            axios.get(apiBaseUrl + 'projects').then(res => {
                this.projects = res.data;
            });
        }
    },
    created() {
        this.fetchProjects();
    }
};
</script>
<template>
    <div class="container">
        <div v-if="projects.length">
            <AppCard :project="project" v-for="project in projects" :key="project.id" />
        </div>
        <h3 v-else class="text-center">Non ci sono progetti</h3>
    </div>
</template>
<style></style>