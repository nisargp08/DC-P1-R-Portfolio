<template>
<div class="all-projects-component lg:max-w-screen-lg lg:mx-auto">
    <app-user-details></app-user-details>
    <app-user-projects :orientation="true"></app-user-projects>
</div>
</template>

<script>
export default {
    name: 'allProjects',
    created(){
        window.scrollTo(0,0);
    },
    components : {
        'appUserDetails': () => import('@/components/UserDetails'),
        'appUserProjects': () => import('@/components/UserProjects'),
    },
}
</script>

<style>

</style>
