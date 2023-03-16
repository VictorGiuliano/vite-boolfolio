<script>
import axios from 'axios';
import AppCard from '../components/AppCard.vue';
const apiBaseUrl = 'http://127.0.0.1:8000/api/';
export default {
    name: 'ProjectDetailPage',
    components: { AppCard },
    data: () => ({
        project: null,
    }),
    methods: {
        getProject() {
            const endpoint = apiBaseUrl + 'projects/' + this.$route.params.id;
            axios.get(endpoint).then(res => {
                this.project = res.data;
            }).catch(err => {
                console.log(err);
            }).then(() => {

            });
        }
    }, created() {
        this.getProject();
    }
};
</script>
<template>
    <AppCard :project="project"></AppCard>
</template>
<style></style>