<template>
<div class="user-skills-component">
    <div class="card">
        <h3 class="font-primary font-bold text-lg uppercase text-gray-2 leading-5">front end</h3>
        <div class="mt-4">
            <!-- Skills loop -->
            <div v-for="(skill,index) in data" :key="index" class="flex items-center mt-4">
                <div class="w-1/3">
                    <p class="font-primary font-medium text-base text-gray-2 break-words">{{skill.name}}</p>
                </div>
                <!-- Skill Bar -->
                <div class="flex-1">
                    <!-- Wrapper -->
                    <div class="bg-gray-1 rounded-12px h-2">
                        <!-- Skill level -->
                        <div :style="{ width : skillLevel(skill.level) }" class="bg-blue-1 bg-opacity-75 rounded-12px h-2"></div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: "userSkills",
    props: {
        data: {
            type: Array,
            required: true,
        }
    },
    methods: {
        //To calculate the width out of 100
        skillLevel(level) {
            let skillLevel;
            //Check if value greater than 100 then width is full
            if (level >= 100) {
                skillLevel = 100 + '%';
            } else {
                //Return in percentage
                skillLevel = Math.floor(level) + '%';
            }
            return skillLevel;
        }
    }
}
</script>

<style>

</style>
