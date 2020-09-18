<template>
  <div class="user-experience-component">
      <div class="card">
          <h3 class="font-primary font-medium text-2xl text-gray-2 leading-8">Experiences</h3>
          <div class="mt-10">
              <div v-for="(job,index) in data" :key="index" class="flex items-center justify-center mt-8">
                  <div class="self-start">
                      <img class="rounded-md w-12" :src="require(`@/assets/images/${job.companyLogo}`)" :alt="job.companyName">
                  </div>
                  <div class="px-4 flex-1">
                      <p class="font-primary font-semibold text-base text-black-1 leading-5">{{job.position}}</p>
                      <p class="font-primary font-medium text-sm leading-4 text-gray-3">{{job.duration}}</p>
                      <p class="font-primary font-medium text-base leading-5 pt-4"><span v-html="job.description"></span></p>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name : 'userExperience',
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