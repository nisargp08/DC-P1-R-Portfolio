<template>
<div class="min-h-screen lg:max-w-screen-lg lg:mx-auto">
    <app-user-details></app-user-details>
    <app-user-experience></app-user-experience>
    <div class="lg:flex">
        <div class="lg:flex lg:flex-col lg:max-w-sm">
            <app-user-skills></app-user-skills>
            <app-user-hobbies></app-user-hobbies>
        </div>
        <div class="lg:flex lg:flex-col">
            <app-user-projects></app-user-projects>
            <app-user-blogs></app-user-blogs>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: "Index",
    components: {
        'appUserDetails': () => import('@/components/UserDetails'),
        'appUserSkills': () => import('@/components/UserSkills'),
        'appUserExperience': () => import('@/components/UserExperience'),
        'appUserBlogs': () => import('@/components/UserBlogs'),
        'appUserHobbies': () => import('@/components/UserHobbies'),
        'appUserProjects': () => import('@/components/UserProjects'),
    },
    created() {
        window.scrollTo(0, 0);
    },
}
</script>

<style lang="scss" scoped>

</style>
