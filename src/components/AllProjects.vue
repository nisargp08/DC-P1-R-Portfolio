<template>
<div class="all-projects-component">
    <app-user-details :data="userInfo"></app-user-details>
    <app-user-projects :orientation="'columns'" :data="projects"></app-user-projects>
</div>
</template>

<script>
export default {
    name: 'allProjects',
    props: {
        userInfo: {
            type: Object,
            required: true,
        },
        projects: {
            type: Array,
            required: true,
        }
    },
    components : {
        'appUserDetails': () => import('@/components/UserDetails'),
        'appUserProjects': () => import('@/components/UserProjects'),
    },
}
</script>

<style>

</style>
