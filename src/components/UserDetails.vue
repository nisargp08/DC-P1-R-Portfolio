<template>
<div class="user-details-component">
    <div class="flex flex-col items-center card md:flex-row md:p-3 lg:items-start">
        <!-- Profile Image -->
        <div class="md:w-1/2">
            <img class="rounded-12px" :src="require(`@/assets/images/${data.profilePhoto}`)" :alt="data.name">
        </div>
        <!-- User Information -->
        <div class="mt-6 md:px-8">
            <div class="md:flex md:items-center md:justify-between">
                <!-- Name & Position -->
                <div>
                    <h1 class="heading">{{data.name}}</h1>
                    <h2 class="subHeading">{{data.position}}</h2>
                </div>
                <!-- Contact Details -->
                <div class="mt-8 md:mt-0">
                    <div class="flex items-center">
                        <div>
                            <svg class="w-6 h-6 fill-current text-gray-2" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" d="M14.243 5.757a6 6 0 10-.986 9.284 1 1 0 111.087 1.678A8 8 0 1118 10a3 3 0 01-4.8 2.401A4 4 0 1114 10a1 1 0 102 0c0-1.537-.586-3.07-1.757-4.243zM12 10a2 2 0 10-4 0 2 2 0 004 0z" clip-rule="evenodd"></path>
                            </svg>
                        </div>
                        <div class="pl-2">
                            <p class="info">{{data.email}}</p>
                        </div>
                    </div>
                    <div class="flex items-center">
                        <div>
                            <svg class="w-6 h-6 fill-current text-gray-2" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" d="M7 2a2 2 0 00-2 2v12a2 2 0 002 2h6a2 2 0 002-2V4a2 2 0 00-2-2H7zm3 14a1 1 0 100-2 1 1 0 000 2z" clip-rule="evenodd"></path>
                            </svg>
                        </div>
                        <div class="pl-2">
                            <p class="info">{{data.phone}}</p>
                        </div>
                    </div>
                </div>
            </div>
            <!-- User Bio -->
            <div class="mt-8 md:mt-10">
                <p class="info" v-html="data.bio"></p>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: "userDetails",
    mounted(){
        //Fetching details from store state
        this.data = this.$store.state.userData;
    },
    data(){
        return{
            //User Details
            data : '',
        }
    }
}
</script>

<style>

</style>
