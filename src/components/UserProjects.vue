<template>
<div class="user-projects-component">
    <div class="card">
        <p class="font-primary font-medium text-lg leading-5 text-gray-2">Projects ({{ data.length }})</p>
    </div>
    <div v-for="(project,index) in data" :key="index" class="card lg:flex lg:items-center">
        <div class="lg:w-1/2">
            <img class="h-64 rounded-12px object-cover mx-auto" :src="require(`@/assets/images/${project.photo}`)" :alt="project.title">
        </div>
        <div class="mt-6 lg:w-1/2 p-4">
            <h3 class="font-primary font-semibold text-xl text-black-1 leading-7">{{ project.title }}</h3>
            <div class="mt-4">
                <p class="font-primary font-medium text-sm leading-5 text-gray-3" v-html="project.description"></p>
            </div>
            <div class="flex mt-4">
              <div v-for="(tag,index) in project.tags" :key="index" class="py-1 px-3 bg-gray-300 rounded-md mr-2">
              <p class="font-primary font-medium text-xs leading-5 text-gray-2">
                #{{ tag }}
              </p>
              </div>
            </div>
            <div class="mt-6">
              <a :href="project.demoUrl" target="_blank" class="font-primary font-medium text-white text-sm leading-6 bg-blue-1 rounded-lg py-1 px-8 border border-blue-1 focus:outline-none hover:bg-blue-500">Demo</a>
              <a :href="project.codeUrl" target="_blank" class="font-primary font-medium text-blue-1 text-sm leading-6 bg-white rounded-lg py-1 px-8 border border-blue-1 ml-2 focus:outline-none hover:bg-gray-300">Code</a>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'userProjects',
    props: {
        data: {
            type: Array,
            required: true,
        }
    }
}
</script>

<style>

</style>
