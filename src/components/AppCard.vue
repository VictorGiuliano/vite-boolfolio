<script>
export default {
    name: 'AppCard',
    props: { project: Object }
};
</script>
<template>
    <div class="card mt-5">
        <div class="card-body">
            <h5 class="card-title">{{ project.title }}</h5>
            <p class="card-text">{{ project.description }}</p>
        </div>
    </div>
</template>