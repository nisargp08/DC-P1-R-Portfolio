<template>
<div class="user-hobbies-component">
    <div class="card">
        <h3 class="font-primary font-medium text-2xl text-gray-2 leading-8">Hobbies</h3>
        <div class="md:flex md:justify-around lg:block">
            <div v-for="(hobby,index) in data" :key="index" class="mt-6 md:w-56 lg:w-full">
                <div>
                    <img class="rounded-12px md:h-48 md:object-cover lg:h-auto" :src="require(`@/assets/images/${hobby.photo}`)" :alt="hobby.title">
                </div>
                <p class="font-primary font-semibold text-lg leading-5 text-black-1 pt-5">{{hobby.title}}</p>
                <p class="font-primary font-medium text-base leading-5 text-gray-3 pt-2">{{hobby.description}}</p>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: "userSkills",
    mounted(){
        //Fetching details from store state
        this.data = this.$store.state.userHobbies;
    },
    data(){
        return{
            //Hobbies
            data : ''
        }
    }
}
</script>

<style>

</style>
