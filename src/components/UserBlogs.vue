<template>
<div class="user-blogs-component lg:w-1/2 lg:w-full">
    <div class="card">
        <p class="font-primary font-medium text-lg leading-5 text-gray-2">Blogs ({{ data.length }})</p>
    </div>
    <div>
        <div v-for="(blog,index) in data" :key="index" class="flex flex-col items-center justify-center card">
            <div class="p-8 md:max-w-sm">
                <!-- Blog Banner image -->
                <img :src="require(`@/assets/images/${blog.blogBanner}`)" :alt="blog.title">
            </div>
            <div>
                <p class="font-primary font-medium text-base leading-5 text-gray-4">Blog</p>
                <!-- Blog title -->
                <div class="mt-6">
                <h3 class="font-primary font-medium text-2xl text-black-1 leading-8">{{blog.title}}</h3>
                </div>
                <!-- Blog Description -->
                <div class="mt-6">
                <p class="font-primary font-medium text-base leading-5 text-gray-3" v-html="blog.description"></p>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'userBlogs',
    mounted(){
        //Fetching details from store state
        this.data = this.$store.state.userBlogs;
    },
    data(){
        return{
            //Blogs
            data : '',
        }
    },
}
</script>

<style>

</style>
