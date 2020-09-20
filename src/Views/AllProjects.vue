<template>
<div class="all-projects-component">
    <!-- <app-user-details :data="userInfo"></app-user-details> -->
    <app-user-projects :orientation="true" :data="projects"></app-user-projects>
</div>
</template>

<script>
export default {
    name: 'allProjects',
    created(){
        window.scrollTo(0,0);
    },
    props: {
    //     // userInfo: {
    //     //     type: Object,
    //     //     required: true,
    //     // },
        projects: {
            type: Array,
            required: true,
        },
    },
    components : {
        // 'appUserDetails': () => import('@/components/UserDetails'),
        'appUserProjects': () => import('@/components/UserProjects'),
    },
}
</script>

<style>

</style>
