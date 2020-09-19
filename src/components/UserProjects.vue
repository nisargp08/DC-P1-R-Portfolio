<template>
<div class="user-projects-component">
    <div class="card">
        <div role="button" v-if="orientation" class="bg-gray-300 inline-block rounded-md p-2 mb-2">
            <svg class="w-4 h-4 fill-current text-gray-800" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                <path d="M8.445 14.832A1 1 0 0010 14v-2.798l5.445 3.63A1 1 0 0017 14V6a1 1 0 00-1.555-.832L10 8.798V6a1 1 0 00-1.555-.832l-6 4a1 1 0 000 1.664l6 4z"></path>
            </svg>
        </div>
        <div class="flex flex-wrap items-center justify-between">
            <p class="font-primary font-medium text-lg leading-5 text-gray-2">Projects ({{ data.length }})</p>
            <button v-if="!orientation" @click="allProjects" class="tag tag-text bg-gray-700 text-white hover:bg-gray-800 focus:outline-none">
                <svg class="w-6 h-6 inline-block" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                    <path d="M9 2a2 2 0 00-2 2v8a2 2 0 002 2h6a2 2 0 002-2V6.414A2 2 0 0016.414 5L14 2.586A2 2 0 0012.586 2H9z"></path>
                    <path d="M3 8a2 2 0 012-2v10h8a2 2 0 01-2 2H5a2 2 0 01-2-2V8z"></path>
                </svg>
                All Projects
            </button>
        </div>
        <div class="flex flex-wrap mt-4">
            <div :class="{'bg-blue-900 hover:bg-blue-900' : tag == selectedTag }" @click="selectedTag = tag" role="button" v-for="(tag,index) in filteredTags" :key="index" class="tag">
                <p class="tag-text" :class="{'text-white' : tag == selectedTag}">
                    #{{tag}}
                </p>
            </div>
            <!-- Remove Filter Button -->
            <button v-if="selectedTag" @click="selectedTag = ''" class="focus:outline-none">
                <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zM8.707 7.293a1 1 0 00-1.414 1.414L8.586 10l-1.293 1.293a1 1 0 101.414 1.414L10 11.414l1.293 1.293a1 1 0 001.414-1.414L11.414 10l1.293-1.293a1 1 0 00-1.414-1.414L10 8.586 8.707 7.293z" clip-rule="evenodd"></path>
                </svg>
            </button>
        </div>
    </div>
    <div>
        <div v-for="(project,index) in filteredProjects" :key="index" class="card lg:flex lg:items-center">
            <div class="lg:w-1/2">
                <img class="h-64 rounded-12px object-contain mx-auto" :src="require(`@/assets/images/${project.photo}`)" :alt="project.title">
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
                    <a v-if="project.demoUrl" :href="project.demoUrl" target="_blank" class="font-primary font-medium text-white text-sm leading-6 bg-gray-700 rounded-lg py-1 px-8 border border-gray-700 focus:outline-none hover:bg-gray-800">Demo</a>
                    <a v-if="project.codeUrl" :href="project.codeUrl" target="_blank" class="font-primary font-medium text-gray-700 text-sm leading-6 bg-white rounded-lg py-1 px-8 border border-gray-700 ml-2 focus:outline-none hover:bg-gray-300">Code</a>
                </div>
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
        },
        orientation: {
            type: String,
            required: false,
        }
    },
    data() {
        return {
            selectedTag: '',
        }
    },
    methods: {
        allProjects() {
            //Emit this click to parent
            this.$emit('all-projects');
        },
    },
    computed: {
        //To return a list of unique tags from the project
        filteredTags() {
            let uniqueTags = [],
                allTags = [];
            //Looping through the data to get unique tags from the list
            this.data.forEach(project => {
                project.tags.forEach(tag => {
                    allTags.push(tag);
                });
            });
            //'Set' function will remove all the duplicates from the array and return only unique values
            //Since 'Set' function return an object 'Array.from' function will convert recieved object into an array
            uniqueTags = Array.from(new Set(allTags));
            return uniqueTags;
        },
        //To return a list of projects which matches the selected tag from the user
        filteredProjects() {
            //IF no tags are selected than return all projects
            if (this.selectedTag == '') {
                return this.data;
            } else {
                let filteredProjects = [];
                //Looping through all the projects to find the clicked tag
                this.data.forEach(project => {
                    //Returning projects that match the tag
                    project.tags.forEach(tag => {
                        if (tag === this.selectedTag) {
                            filteredProjects.push(project);
                        }
                    })
                })
                return filteredProjects;
            }
        }
    }
}
</script>

<style>

</style>
