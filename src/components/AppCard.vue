<script>
import { RouterLink } from 'vue-router';

export default {
    name: "AppCard",
    props: { project: Object },
    components: { RouterLink }
};
</script>
<template>
    <div class="card mt-5">
        <div class="card-body">
            <h5 class="card-title">{{ project.title }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <RouterLink class="btn btn-primary" :to="{ name: 'show', params: { id: project.id } }">Vai al dettaglio
            </RouterLink>
        </div>
    </div>
</template>